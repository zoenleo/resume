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
        let rotateZ = 0,
            width = 800
        const dom: any = this.$refs.blackhole
        setInterval(() => {
            rotateZ += 2
            if (rotateZ > 360) {
                rotateZ = 0
            }
            dom.style.transform = `rotateZ(${rotateZ}deg)`
        }, 36)
        setInterval(() => {
            width = width > 700 ? 700 : 800
            dom.style.width = width + 'px'
        }, 3000)
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
        transition: width 3s;
        transition-timing-function: cubic-bezier(0.34, 0, 0.84, 1);
    }
}
</style>
