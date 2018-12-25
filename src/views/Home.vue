<template>
    <div class="home">
        <img alt="Vue logo" src="../assets/logo.png" />
        <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import HelloWorld from '@/components/HelloWorld.vue' // @ is an alias to /src

interface methodsType {
    alert: () => void
}

@Component({
    components: {
        HelloWorld
    }
})
export default class Home extends Vue {
    private msg = 'Welcome to Your Vue.js + TypeScript App'
    alert() {
        console.log(this.$refs.helloworld)
        this.msg = 'alert'
    }
}
</script>

<style lang="scss">
img:hover {
    transform: rotate(666turn);
    transition-delay: 1s;
    transition-property: all;
    transition-duration: 59s;
    transition-timing-function: cubic-bezier(0.34, 0, 0.84, 1);
}
</style>
