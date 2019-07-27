<template>
<div class="problem">
    <div class="problem_text">
        <headers></headers>
        <div class="problem">
            <div class="problem_banner">
                <!-- <img src="../../assets/images/income_01.png" alt=""> -->
            </div>
            <div class="problem_con" id="problem_active1">
                <div class="problem_title">问题&反馈</div>
                <div class="problem_list">
                    <div class="title">
                        常见问题
                    </div>
                    <el-collapse v-model="activeNames" @change="handleChange">
                        <el-collapse-item title="一个西柚机账号可以多人通过APP共享使用吗？" name="1">
                            <div>目前一个西柚机同一时间只能被一个用户绑定使用，但可以通过解绑再绑定给其他用户使用</div>
                        </el-collapse-item>
                        <el-collapse-item title="更换了手机号如何更换我的西柚机账号？" name="2">
                            <div>在APP的个人信息设置中可进行手机号更换，更换手机号后，使用新手机号登录即可查看原手机的绑定的西柚机相关信息</div>
                        </el-collapse-item>
                        <el-collapse-item title="一个账号可以在多个手机上同时登录吗?" name="3">
                            <div>为了保障用户的登录安全，我们限定了同一时间只能在一个手机设备上进行APP的操作</div>

                        </el-collapse-item>
                        <el-collapse-item title="西柚机需要外接硬盘吗？" name="4">
                            <div>西柚机内部自带硬盘，不需要外接硬盘</div>
                        </el-collapse-item>
                    </el-collapse>
                    <!-- <van-collapse v-model="activeNames">
                        <van-collapse-item title="一个西柚机账号可以多人通过APP共享使用吗？" name="1">目前一个西柚机同一时间只能被一个用户绑定使用，但可以通过解绑再绑定给其他用户使用</van-collapse-item>
                        <van-collapse-item title="更换了手机号如何更换我的西柚机账号？" name="2">在APP的个人信息设置中可进行手机号更换，更换手机号后，使用新手机号登录即可查看原手机的绑定的西柚机相关信息</van-collapse-item>
                        <van-collapse-item title="一个账号可以在多个手机上同时登录吗?" name="3">为了保障用户的登录安全，我们限定了同一时间只能在一个手机设备上进行APP的操作</van-collapse-item>
                        <van-collapse-item title="西柚机需要外接硬盘吗？" name="4">西柚机内部自带硬盘，不需要外接硬盘</van-collapse-item>
                    </van-collapse> -->
                </div>
            </div>
            <div class="problem_con1" id="problem_active2">
                <div class="problem_total">
                    <div class="problem_title">意见反馈</div>
                    <div class="problem_sumit">
                        <div class="item_input">
                            <input type="text" v-model="userName" placeholder="姓名">
                        </div>

                        <div class="item_input">
                            <input type="text" v-model="userTel" placeholder="联系方式">
                        </div>

                    </div>
                    <div class="problem_textarea">
                        <textarea placeholder="问题描述" v-model="userquestion"></textarea>
                        <p>若需要得到回复，请填写联络方式</p>
                    </div>
                    <div class="item_bottom">
                        <div class="item_button" @click="onSumit()">提交</div>
                    </div>
                </div>
            </div>
        </div>

        <div class="xy_footer">
            <div class="xy_footer_con">
                <div class="item">
                    <div class="item_h2">购买方式</div>
                    <div class="item_con" @click="goLink2()">点击购买</div>

                </div>
                <div class="item">
                    <div class="item_h2">服务支持</div>
                    <div class="item_con" @click="goLink3()">常见问题</div>
                    <div class="item_con" @click="goLink4()">意见反馈</div>
                </div>
                <div class="item">
                    <div class="item_h2">关于我们</div>
                    <div class="item_con" @click="goto('privacy','problem_active3')">隐私声明</div>
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
</div>
</template>

<script>
import headers from '../../components/header'
import footers from '../../components/footer'
import {
    savequestion,

} from '../../common/js/api.js'
export default {
    data() {
        return {

            userName: "",
            userTel: "",
            userquestion: "",
            activeNames: []

        };
    },
    created: function () {
        this.$nextTick(() => {
            this.getlocal()
        })
    },
    mounted: function () {

        let that = this;
        that.$nextTick(function () {
            window.addEventListener('scroll', that.handleScroll)
        })
        // this.initVideo();
    },
    methods: {
        onSumit() {
            let param = new Object()
            param.login_token = localStorage.getItem('userToken')
            if (param.login_token == null || param.login_token == "") {
                this.$message({
                    message: '请登录后在提交意见反馈',
                    type: 'error'
                });
                return false
            }
            param.user_tel_num = this.userTel
            param.quest_cotent = this.userquestion
            param.user_name = this.userName
            //param.login_type = 2

            savequestion(param).then(res => {
                if (res.status != 0) {
                    this.$message({
                        message: '网络错误，请重新提交',
                        type: 'error'
                    });
                } else {
                    this.$message({
                        message: '提交成功',
                        type: 'success'
                    });

                }

            }).catch(error => {

            })

        },
        goLink2() {
            this.$router.push({
                path: "/buying"
            })
        },
        getlocal() {

            //找到锚点id
            let selectId = localStorage.getItem("toId");
            let toElement = document.getElementById(selectId);
            //如果对应id存在，就跳转
            if (selectId) {
                toElement.scrollIntoView()
            }
        },
        goLink3() {
            const returnEle = document.querySelector("#problem_active1");
            if (!!returnEle) {
                returnEle.scrollIntoView(true);
            }
        },
        goLink4() {
            const returnEle = document.querySelector("#problem_active2");
            if (!!returnEle) {
                returnEle.scrollIntoView(true);
            }
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
    destroyed() {
        localStorage.setItem("toId", '')
    },
    components: {
        headers: headers,
        footers: footers
    }

};
</script>

<style lang="less" scoped>
.van-cell {
    font-size: 24px;
}

.problem {
    width: 100%;
    height: auto;
    margin: 0 auto;

    .problem_banner {
        background: url(../../assets/images/param.png) no-repeat center;
        width: 100%;
        height: 679px;
        z-index: 10;
    }

    // .income_banner {
    //     img {
    //         width: 7.5rem;
    //         height: 5.29rem;
    //     }
    // }

    .problem_con {
        width: 1200px;
        height: auto;
        overflow: hidden;
        margin: 0 auto;

        .problem_title {
            color: #000000;
            font-size: 0.60rem;
            width: 6rem;
            margin: 0.5rem auto;
            text-align: center;
        }

        .title {
            font-size: 42px;

            font-weight: 500;
            color: rgba(0, 0, 0, 1);
            margin-bottom: 20px;
        }

        .van-cell {

            font-size: 24px !important;
            font-weight: normal;
            color: rgba(0, 0, 0, 1);
        }
    }

    .problem_list {
        margin-bottom: 0.5rem;
    }

    .problem_con1 {
        width: 100%;
        height: auto;
        background: #F9F9F9;
        overflow: hidden;

        .problem_total {
            width: 1200px;
            height: auto;
            margin: 0 auto;
        }

        .problem_title {
            color: #000000;
            font-size: 0.36rem;
            width: 6rem;
            margin-top: 70px;

        }

        .problem_sumit {
            width: 1200px;
            height: auto;
            overflow: hidden;
            margin: 0rem auto;
            margin-top: 0.3rem;
            display: flex;
            justify-content: space-between;
            align-items: center;

            .item_input {
                width: 580px;
                height: auto;
                margin-top: 0.3rem;

                p {
                    color: #808080;
                    font-size: 0.12rem;
                }

                input {
                    width: 575px;
                    height: 0.55rem;
                    background: rgba(255, 255, 255, 1);
                    border: 1px solid #6D6D6D;
                    border-radius: 0.05rem;
                    text-indent: 0.2rem;
                    font-size: 24px;
                }

                textarea {
                    width: 575px;
                    height: 1.55rem;
                    background: rgba(255, 255, 255, 1);
                    border: 1px solid #6D6D6D;
                    border-radius: 0.05rem;
                    text-indent: 0.1rem;
                    outline: none;
                }

                .item_button {
                    width: 2.27rem;
                    height: 0.70rem;
                    background: rgba(36, 36, 36, 1);
                    border-radius: 0.35rem;
                    font-size: 0.26rem;
                    color: #ffffff;
                    margin: 0.5rem auto;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                }
            }
        }

        .problem_textarea {
            width: 1200px;
            height: auto;
            margin: 0 auto;
            margin-top: 40px;

            textarea {
                width: 850px;
                height: 1.55rem;
                background: rgba(255, 255, 255, 1);
                border: 1px solid #6D6D6D;
                border-radius: 0.05rem;
                text-indent: 0.1rem;
                outline: none;
                font-size: 24px;

            }

            p {
                color: #808080;
                font-size: 16px;
                margin-top: 10px;
            }
        }

        .item_bottom {
            width: 1200px;
            height: auto;
            margin: 0 auto;
            margin-top: 40px;
            margin-bottom: 60px;

            .item_button {
                width: 350px;
                height: 76px;
                background: rgba(36, 36, 36, 1);
                border-radius: 38px;
                margin: 0 auto;
                line-height: 76px;
                text-align: center;
                font-size: 30px;

                font-weight: normal;
                color: rgba(255, 255, 255, 1);
                cursor: pointer;
            }
        }
    }
}

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
