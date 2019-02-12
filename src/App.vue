<template>
    <div id="app">
        <div :class="{ dropApp: drop, appContent: true }">
            <div id="nav">
                <router-link to="/">个人简介</router-link> |
                <router-link to="/about">专业技能</router-link>
            </div>
            <router-view />
        </div>
    </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator'
import BlackHole from '@/components/BlackHole.vue' // @ is an alias to /src
import Drop from '@/components/Drop.vue' // @ is an alias to /src
@Component({
    components: {
        BlackHole,
        Drop
    }
})
export default class App extends Vue {
    drop = false
    scale = false
    timeoutId = 0
    onDropClick() {
        if (this.scale) return
        if (this.drop) {
            this.drop = false
            return
        }
        this.drop = true
        this.scale = true
        this.timeoutId = setTimeout(() => {
            this.scale = false
        }, 5000)
    }
}
</script>

<style lang="scss">
@import './theme/global.scss';
@import './theme/variable.scss';
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    background-color: $theme-bgcolor;
    padding-bottom: 100px;
    min-height: 100%;
}

.appContent {
    transform: rotateZ(0) scale(1);
    transition: transform 5s;
}

.dropApp {
    transform-origin: 50% 110%;
    transform: rotateZ(3turn) scale(0);
}

#nav {
    padding: 30px;
    background-color: $theme-color;
    box-shadow: 0 0 2px 2px rgba(199, 100, 125, 0.3);
    a {
        font-weight: bold;
        color: #2c3e50;
        &.router-link-exact-active {
            color: #42b983;
        }
    }
}

@media (min-width: 1401px) {
    #app {
        width: 1080px;
        margin-left: auto;
        margin-right: auto;
    }
}

@media (max-width: 1400px) {
    #app {
        margin-left: 160px;
        margin-right: 160px;
    }
}

@media (max-width: 1280px) and (min-width: 1025px) {
    #app {
        width: 960px;
        margin-left: auto;
        margin-right: auto;
    }
}

@media (max-width: 1024px) {
    #app {
        margin-left: 40px;
        margin-right: 40px;
    }
}

@media (max-width: 500px) {
    #app {
        margin-left: 0;
        margin-right: 0;
    }
}
</style>
