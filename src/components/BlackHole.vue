<template>
    <div class="black-hole">
        <img ref="blackhole" src="../assets/blackhole.png" alt="黑洞" />
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class BlackHole extends Vue {
    mounted() {
        let width = 800
        const dom: any = this.$refs.blackhole
        dom.style.transform = 'rotateZ(3turn)'
        setInterval(() => {
            width -= 10
            dom.style.width = width + 'px'
        }, 100)
    }
}
</script>

<style scoped lang="scss">
.black-hole {
    position: fixed;
    z-index: 1;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    background: rgba(200, 200, 200, 0.3);
    img {
        position: absolute;
        left: 0;
        right: 0;
        top: 0;
        bottom: 0;
        margin: auto;
        width: 800px;
        transition: transform 9s;
        &:hover {
            transform: rotateZ(3turn);
        }
    }
}
</style>
