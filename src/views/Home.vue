<template>
    <div class="home">
        <div class="avatar"></div>
        <Me :msg="msg" @alert="alert" />
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import Me from '@/components/Me.vue' // @ is an alias to /src
@Component({
    components: {
        Me
    }
})
export default class Home extends Vue {
    private msg: string = ''
    data() {
        return {
            msg: 'Welcome to Your Vue.js + TypeScript App'
        }
    }
    alert(e: Event) {
        this.msg = 'alert'
    }
}
</script>

<style lang="scss">
.home {
    padding-top: 50px;
    .avatar {
        width: 100px;
        height: 100px;
        margin: 0 auto;
        border-radius: 50%;
        background: url('../assets/avatar.jpeg') no-repeat;
        background-size: cover;
        transform: rotateZ(0deg);
        transition-property: transform;
        transition-duration: 1s;
        transition-timing-function: cubic-bezier(0.34, 0, 0.84, 1);
        &:hover {
            transform: rotateZ(360deg);
        }
    }
}
</style>
