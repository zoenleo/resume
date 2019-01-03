<template>
    <div class="me">
        <h1>{{ msg }}</h1>
        <h1 @click="onClick">{{ message }}</h1>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

interface HelloWorldProps {
    msg: string
    alert: () => void
}

@Component
export default class HelloWorld<HelloWorldProps> extends Vue {
    @Prop() private msg!: string
    data() {
        return {
            message: 'hello world!'
        }
    }
    onClick(e: Event) {
        this.$emit('alert', e)
    }
}
</script>

<style scoped lang="scss">
.me {
    h1 {
        margin: 40px 0 0;
    }
    ul {
        list-style-type: none;
        padding: 0;
    }
    li {
        display: inline-block;
        margin: 0 10px;
    }
    a {
        color: #42b983;
    }
}
</style>
