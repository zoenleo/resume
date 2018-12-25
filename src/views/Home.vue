<template>
    <div class="home">
        <div class="avatar"></div>
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
.avatar {
    width: 100px;
    height: 100px;
    margin: 0 auto;
    border-radius: 50%;
    background: url('../assets/avatar.jpeg') no-repeat;
    background-size: cover;
    &:hover {
        transform: rotateZ(360deg);
        transition-property: all;
        transition-duration: 1s;
        transition-timing-function: cubic-bezier(0.34, 0, 0.84, 1);
    }
}
</style>
