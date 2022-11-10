<template>
    <div class="me">
        <p>
            刘重，1992年生，湖南长沙人。15年于
            <a href="http://www.csust.edu.cn/index.htm" target="_blank"
                >长沙理工大学</a
            >
            毕业，现居于深圳，就职于微众银行，前端开发工程师。
        </p>
        <p>
            毕业怀着一颗北漂梦去了北京，进入了我正式职业生涯的第一家公司
            <a href="https://www.supermap.com/cn/" target="_blank">超图软件</a>
            ，也是作为前端开发。公司平台很大，非常感谢公司的知遇之恩，也常常怀念公司老同事，后因环境和个人原因离开了北京。
        </p>
        <p>
            后来在朋友的邀请下来到了深圳，也是我最喜欢的一个城市，入职前公司
            <a href="http://www.ky-express.com/" target="_blank"
                >跨越速运集团</a
            >
            ，刚开始作为前端开发进入，后被提拔为前端开发组长。
        </p>
        <p>
            之后由于公司恶意裁员，我受不了的情下主动离职，入职现在的公司
            <a href="https://www.webank.com/" target="_blank">微众银行</a>。
            在公司内老大给我机会，让我带团队与沟通业务，在这里我学到了代码之外的其他东西，对老大和公司只有感激还是感激，经常感叹这是我遇到最好的老大。
        </p>
        <p style="color: #996666">现在由于公司业务调整，即将被毕业，找工作中~</p>
        <p>喜欢折腾，希望未来能以技术做出自己满意的东西。</p>
        <p>
            热爱开源，有在写自己的技术博客，常看掘金、gitbub、奇舞周刊、知乎，贡献过npm开源项目。
        </p>
        <p>对代码有一定要求，常常推动现在公司代码规范进步，喜欢code review。</p>
        <p>
            联系方式：<a href="mailto:lz271253196@.com"
                >lz271253196@qq.com</a
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
