<template>
<div>

    <div class="xy_footer">
        <div class="xy_footer_con">
            <div class="item">
                <div class="item_h2">购买方式</div>
                <div class="item_con" @click="goLink2()">点击购买</div>

            </div>
            <div class="item">
                <div class="item_h2">服务支持</div>
                <div class="item_con" @click="goto('problem','problem_active1')">常见问题</div>
                <div class="item_con" @click="goto('problem','problem_active2')">意见反馈</div>
            </div>
            <div class="item">
                <div class="item_h2">关于我们</div>
                <div class="item_con"  @click="goto('privacy','problem_active3')">隐私声明</div>
                <div class="item_con" @click="goto('protocol','problem_active4')">用户协议</div>

            </div>
            <div class="item">
                <div class="item_h2">联系我们</div>
                <div class="item_con">在线QQ</div>
                <div class="item_con">231155479</div>
                <div class="item_con">微信</div>
                <div class="item_con">12345667892</div>
                <div class="item_con">客服电话</div>
                <div class="item_con">01234567(9:00-18:00)</div>
            </div>

        </div>
        <div class="item_address">

            <p> Copyright©2016-2018 XXXX lnc</p>
            <p>北京西柚网络科技有限公司保留所有权 京工网安备案 123456 号 京ICP 备 123456 号 -1
            </p>
        </div>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {

        }
    },
    mounted: function () {

    },
    methods: {
        goLink() {
            this.$router.push({
                path: "/privacy"
            })
        },
        goLink1() {
            this.$router.push({
                path: "/protocol"
            })
        },
        goLink2() {
            this.$router.push({
                path: "/buying"
            })
        },
        goLink3() {
            this.$router.push({
                path: "/problem"
            })
        },
        goLink4() {
            this.$router.push({
                path: "/problem"
            })
        },
        goto(page, selectId) {
            var path = page;
            var selectId = selectId;
            localStorage.setItem("toId", selectId);
            this.$router.push({
                path: path
            })
        },

    },
    // destroyed() {
    //     localStorage.setItem("toId", '')
    // },

}
</script>

<style lang="less">
.xy_footer {
    width: 100%;
    height: auto;
    overflow: hidden;
    background: #242424;

    .xy_footer_con {
        width: 900px;
        height: auto;
        margin: 0 auto;
        display: flex;
        justify-content: center;

    }

    .item {
        width: 50%;
        height: auto;
        float: left;
        overflow: hidden;
        margin-top: 70px;
        margin-bottom: 60px;

        .item_h2 {
            font-size: 22px;
            color: #808080;
            text-align: left;
            padding-left: 0rem;
            box-sizing: border-box;
        }

        .item_con {
            font-size: 18px;
            color: #F7F7F7;
            text-align: left;
            padding-left: 0rem;
            box-sizing: border-box;
            font-weight: 100;
            margin-top: 0.1rem;
            cursor: pointer;

            .kf_button {
                width: 1.87rem;
                height: 0.55rem;
                border: 1px solid rgba(206, 206, 206, 1);
                color: #FFFFFF;
                border-radius: 27px;
                display: flex;
                justify-content: space-around;
                align-items: center;
                cursor: pointer;

                img {
                    width: 0.44rem;
                    height: 0.44rem;
                }
            }
        }

    }

    .item_address {
        width: 100%;
        height: 80px;
        border-top: 1px solid #ffffff;
        text-align: center;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;

        p {
            color: #4A4A4A;
            margin-top: 10px;
        }

    }
}
</style>
