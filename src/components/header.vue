<template>
<div class="xy_header">
    <div class="xy_header_con">
        <div class="xy_logo">
            <img src="../assets/images/pc_logo.png" alt="" @click="returnComactive3">
        </div>
        <div class="xy_logo_nav">
            <div class="item" @click="goto('/','comment4')">首页</div>
            <div class="item item_active1" @click="goto('/','comment')">产品介绍</div>
            <div class="item" @click="returnCom7">推广计划</div>
            <div class="item" @click="goto('/','comment1')">APP下载</div>
             <div class="item" @click="returnComactive2">收益介绍</div> 

            <div class="item" @click="goto('/','comment3')">联系我们</div>

            <div class="item" v-show="!loginStatus" @click="returnComactive1">登录</div>
            <div class="item item_active" v-show="loginStatus" @click="goUsercenter()">
                <img src="../assets/images/timg1.png" width="50" height="50">
                <!-- <div>{{this.username}}</div> -->
            </div>

        </div>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {
            loginStatus: false,
            username: ""

        }
    },
    mounted: function () {
        this.loginStatus = localStorage.getItem('loginStatus')
        if (this.loginStatus == null) {
            this.loginStatus = false
        }
        this.username = localStorage.getItem('nowusername')
        this.$forceUpdate()

    },
    methods: {
        goto(page, selectId) {
            var path = page;
            var selectId = selectId;
            localStorage.setItem("toId", selectId);
            this.$router.push({
                path: path
            })
        },

        returnComactive() {

        },
        returnComactive3() {
            this.$router.push({
                path: '/'
            })
        },
        returnCom10() {
            this.$router.push({
                path: '/problem'
            })
        },
        returnComactive1() {
            this.$router.push({
                path: "/loginactive"
            })
        },
        returnComactive2() {
            this.$router.push({
                path: "/param"
            })
        },
        returnCom7() {
            this.$router.push({
                path: "/promotion"

            })

        },
        goUsercenter(){
             this.$router.push({
                path: "/management"

            })
        }
    }
}
</script>

<style lang="less" scoped>
.publicbetween {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.xy_header {
    width: 100%;
    height: 80px;
    background: rgba(36, 36, 36, 1);

    .xy_header_con {
        width: 1150px;
        height: 80px;
        margin: 0 auto;
        .publicbetween;
    }

    .xy_logo {
        cursor: pointer;
    }

    .xy_logo_nav {
        .publicbetween;

        .item {
            color: #D9D9D9;
            font-size: 18px;
            margin-right: 30px;
            cursor: pointer;
        }

        .item_active {
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;

            img {
                margin-right: 10px;
            }
        }
    }
}
</style>
