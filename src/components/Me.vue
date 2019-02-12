<template>
    <div class="me">
        <p>
            刘重，1992年生，湖南长沙人。15年于
            <a href="http://www.csust.edu.cn/index.htm" target="_blank"
                >长沙理工大学</a
            >
            毕业，现居于深圳，就职于跨越速运集团，前端开发工程师。
        </p>
        <p>
            毕业怀着一颗北漂梦去了北京，进入了我正式职业生涯的第一家公司
            <a href="https://www.supermap.com/cn/" target="_blank">超图软件</a>
            ，也是作为前端开发。公司平台很大，非常感谢公司的知遇之恩，也常常怀念公司老同事，后因环境和个人原因离开了北京。
        </p>
        <p>
            17年到广州就职
            <a href="http://www.amoebait.com/" target="_blank"></a>
            阿米巴网络科技有限公司，公司很有活力，纯互联网公司，老大是从阿里出来的创业者，口才与技术并重。在阿米巴度过了我职业生涯中最大的提升期，感谢立哥老大的信任与培养。
        </p>
        <p>
            后来在朋友的邀请下来到了深圳，也是我最喜欢的一个城市，入职我现在的公司
            <a href="http://www.ky-express.com/" target="_blank"
                >跨越速运集团</a
            >
            ，职位前端开发组长。
        </p>
        <p>喜欢折腾，希望未来能以技术做出自己满意的东西。</p>
        <p>
            热爱开源，有在写自己的技术博客，常看掘金、gitbub、奇舞周刊、知乎，贡献过npm开源项目。
        </p>
        <p>对代码有一定要求，常常推动现在公司代码规范进步，喜欢code review。</p>
        <p>
            联系方式：<a href="mailto:lz271253196@gmail.com"
                >lz271253196@gmail.com</a
            >
        </p>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class HelloWorld<HelloWorldProps> extends Vue {
    @Prop() private msg!: string
}
</script>

<style scoped lang="scss">
.me {
    padding-top: 50px;
    text-align: left;
    padding-top: 50px;
    font-size: 20px;
    color: #606c71;
    line-height: 26px;
    p {
        padding: 10px 20px;
    }
    a {
        text-decoration: none;
    }
}
</style>
