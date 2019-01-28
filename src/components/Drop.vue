<template>
    <div class="drop" @click="onClick" @mousemove="onMouseMove" :style="style">
        {{ drop ? '再给一次机会' : '丢进垃圾桶' }}
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

interface HelloWorldProps {
    click: () => void
}

@Component
export default class HelloWorld<HelloWorldProps> extends Vue {
    @Prop() drop = false
    style = {
        '--y': '0',
        '--x': '0'
    }
    onClick(e: Event) {
        this.$emit('click', e)
    }
    onMouseMove(e: { offsetX: number; offsetY: number }) {
        this.style = {
            '--y': e.offsetY + 'px',
            '--x': e.offsetX + 'px'
        }
    }
}
</script>

<style scoped lang="scss">
@import '@/theme/variable.scss';
.drop {
    position: fixed;
    z-index: 1;
    bottom: 100px;
    right: 40px;
    font-size: 14px;
    display: inline-block;
    padding: 10px 15px;
    border-radius: 5px;
    border: 1px solid rgb(243, 81, 52);
    background-color: rgb(243, 81, 52);
    color: #fff;
    overflow: hidden;
    cursor: pointer;
    &::after {
        content: '';
        position: absolute;
        z-index: 1;
        width: 0;
        height: 0;
        box-shadow: 0 0 0 0 rgba(44, 05, 166, 1);
    }
    &:hover::after {
        left: var(--x, 0);
        top: var(--y, 0);
        /* background: radial-gradient(circle closest-side, #4405f7, transparent);
        transform: translate(-50%, -50%);
        transition: width .2s ease, height .2s ease;
        width: 200px;
        height: 200px; */
        box-shadow: 0 0 150px 50px #4405f7;
        transition: box-shadow 0.2s ease;
    }
}
</style>
