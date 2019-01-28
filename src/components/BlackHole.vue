<template>
    <div class="black-hole" v-show="scale">
        <img
            ref="blackhole"
            :class="{ scale }"
            src="../assets/blackhole.png"
            alt="黑洞"
        />
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class BlackHole extends Vue {
    @Prop() scale = false
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
        transform: rotateZ(0);
        transition: transform 5s linear;
    }
    .scale {
        animation: animate 5s linear;
        transform: rotateZ(2turn);
    }
}

@keyframes animate {
    from {
        width: 800px;
    }
    30% {
        width: 600px;
    }
    70% {
        width: 800px;
    }
    to {
        width: 400px;
    }
}
</style>
