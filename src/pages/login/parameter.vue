<template>
<div class="introduction">
    <headers></headers>
    <div class="buy_con">
        <div class="item_con">
            <div class="item_l">西柚机</div>
            <div class="item_r">
                <div class="p1" @click="goParam()">参数</div>
                <div class="p2 active" @click="goBuying()">购买</div>
            </div>
        </div>
    </div>
    <div class="parameter">
        <div class="item_con1">
            <div class="item_h2">产品参数</div>
            <div class="item_img"><img src="../../assets/images/param_01.png" alt=""></div>
            <div class="item_xh">
                <div class="item_icon"></div>
                <div class="item_text">黑曜石</div>
            </div>
        </div>
        <div class="item_con2 item_con1">
            <div class="item_h2 active">发烧级配置</div>
            <div class="item_img">
                <div class="img_con" style="margin-top:20px;">
                    <div class="item_boador">
                        <p><img src="../../assets/images/cpu_icon1.png" alt=""></p>
                        <p class="text_active1">CPU</p>
                        <p class="text_active2">四核1.5GHZ</p>
                    </div>
                    <div class="item_boador">
                        <p><img src="../../assets/images/cpu_icon1_01.png" alt=""></p>
                        <p class="text_active1">RAM</p>
                        <p class="text_active2">2GB DDR3</p>
                    </div>
                    <div class="item_boador">
                        <p><img src="../../assets/images/cpu_icon1_02.png" alt=""></p>
                        <p class="text_active1">ROM</p>
                        <p class="text_active2">8GB eMMC</p>
                    </div>
                </div>
                <div class="img_con">
                    <div class="item_boador">
                        <p><img src="../../assets/images/cpu_icon1_03.png" alt=""></p>
                        <p class="text_active1">GPU</p>
                        <p class="text_active2">Mali 450 </p>
                    </div>
                    <div class="item_boador">
                        <p><img src="../../assets/images/cpu_icon1_04.png" alt=""></p>
                        <p class="text_active1">HD</p>
                        <p class="text_active2">1TB 5400转</p>
                    </div>
                    <div class="item_boador">
                        <p><img src="../../assets/images/hdmi_icon.png" alt=""></p>
                        <p class="text_active1">HDMI</p>
                        <p class="text_active2">4K 60Hz HDCP</p>
                    </div>
                </div>
            </div>
            <div class="item_bottom">

            </div>
        </div>
        <div class="item_con1 item_con3 item_con2">
            <div class="item_h2">尺寸与重量</div>
            <div class="item_img"><img src="../../assets/images/param_02active.png" alt=""></div>
            <div class="item_xh">
                <div class="item_text">重量：1000g</div>
            </div>
            <div class="item_bottom">

            </div>
        </div>
        <div class="item_con1 item_con4 item_con2">
            <div class="item_h2">硬件配置</div>
            <div class="item_img item_img_active">
                <div><img src="../../assets/images/param_03.png" alt=""></div>
                <div class="item_param">
                    <p>CPU<span>四核1.5GHZ</span></p>
                    <p>GPU<span>Mali 450</span></p>
                    <p>RAM<span>2GB DDR3</span></p>

                </div>
            </div>

            <div class="item_bottom">

            </div>
        </div>
        <div class="item_con5 item_con2">
            <div class="item_h2">接口配置</div>
            <div class="item_p">
                <p>RJ45x1<span>（千兆网1000Mbps）</span></p>
                <p>USB3.0 ×2<span>支持多种扩展</span></p>
            </div>
            <div class="item_bottom">

            </div>
        </div>
        <div class="item_con5 item_con2">
            <div class="item_h2">其他配置</div>
            <div class="item_p">
                <p>电源适配器<span>DC ∮5.5mm,12V/1.5A</span></p>
                <p>网线<span>1米标准线材 </span></p>
            </div>
            <div class="item_bottom">

            </div>
        </div>
        <div class="item_con5 item_con2">
            <div class="item_h2">材质</div>
            <div class="item_p">
                <p>铝合金（表面喷砂）</p>
            </div>
            <div class="item_bottom">

            </div>
        </div>
        <div class="item_con5 item_con2">
            <div class="item_h2">系统</div>
            <div class="item_p">
                <p>Android7.1</p>
            </div>
            <div class="item_bottom">

            </div>
        </div>
        <div class="item_con5 ">
            <div class="item_h2">指导价</div>
            <div class="item_p">
                <p>998RMB</p>
            </div>

        </div>
    </div>
    <footers></footers>

</div>
</template>

<script>
import headers from '../../components/header'
import footers from '../../components/footer'

export default {
    data() {
        return {};
    },
    mountod: function () {},
    methods: {
        goParam() {
            this.$router.push({
                path: "/parameter"
            })
        },
        goBuying() {
            this.$router.push({
                path: "/buying"

            })
        }

    },
    components: {
        headers: headers,
        footers: footers
    }

};
</script>

<style lang="less" scoped>
.publicbetween {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.introduction {
    width: 100%;
    height: auto;
    overflow: hidden;

    .buy_con {
        width: 100%;

        height: 87px;
        background: rgba(250, 250, 250, 1);

        .item_con {
            width: 1150px;
            height: 87px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;

            .item_l {
                font-size: 30px;
                font-weight: bold;
                color: rgba(36, 36, 36, 1);
                line-height: 24px;
            }

            .item_r {
                color: #808080;
                font-size: 26px;
                display: flex;
                justify-content: space-between;
                align-items: center;

                div {
                    margin-right: 50px;
                    cursor: pointer;
                    width: 97px;
                    height: 43px;
                    background: #ffffff;
                    border-radius: 22px;
                    font-size: 26px;
                    font-weight: bold;

                    line-height: 24px;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    text-align: center;
                    margin-right: 50px;

                    &:hover {
                        width: 97px;
                        height: 43px;
                        background: rgba(36, 36, 36, 1);
                        border-radius: 22px;
                        font-size: 26px;
                        font-weight: bold;
                        color: rgba(254, 254, 254, 1);
                        line-height: 24px;
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        text-align: center;
                        margin-right: 50px;

                    }
                }

            }
        }
    }
}

.parameter {
    width: 100%;
    height: auto;
    overflow: hidden;

    .item_con1 {
        width: 1150px;
        height: auto;
        margin: 0 auto;

        .item_bottom {
            width: 1150px;
            height: auto;
            background: rgba(144, 144, 144, 1);
            opacity: 0.5;
            margin: 0 auto;
            margin-bottom: 0.5rem;
            margin-top: 0.5rem;

        }

        .item_img {
            margin-bottom: 0.2rem;
            margin: 0 auto;
            text-align: center;

            img {
                // border: 1px dashed #999999;
            }

        }

        .item_h2 {
            color: #000000;

            font-size: 42px;
            margin: 0.5rem auto;
            margin-top: 50px;
            margin-bottom: 20px;

            &.active {
                font-size: 36px;
            }
        }

        .item_xh {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 1.5rem;
            margin: 0 auto;
            margin-top: 30px;

            .item_icon {
                width: 0.39rem;
                height: 0.39rem;
                border: 1px solid rgba(100, 100, 100, 1);
                border-radius: 50%;
                background: #23221F;
            }

            .item_text {
                font-size: 0.24rem;
                font-weight: 400;
                color: rgba(128, 128, 128, 1);
            }
        }
    }

    .item_con2 {
        margin-top: 0.2rem;
        overflow: hidden;

        .item_img {
            .img_con {
                display: flex;
                justify-content: space-around;
                align-items: center;
                margin-top: 100px;
                margin-bottom: 100px;

                img {
                    width: 51px;
                    height: 51px;
                }

                .item_boador {
                    width: 204px;
                    height: 207px;
                    border: 1px solid rgba(128, 128, 128, 1);
                    border-radius: 0.04rem;
                    display: flex;
                    align-items: center;
                    flex-direction: column;
                    justify-content: center;

                    .text_active1 {
                        font-size: 28px;
                        margin-top: 30px;
                    }

                    .text_active2 {
                        font-size: 22px;
                    }
                }
            }
        }

        .item_bottom {
            width: 1150px;
            height: 1px;
            background: rgba(144, 144, 144, 1);
            opacity: 0.5;
            margin: 0 auto;
            margin-bottom: 0.5rem;
            margin-top: 0.5rem;
        }
    }

    .item_con3 {
        .item_img {
            margin-bottom: 0.2rem;

            img {
                width: 509px;
                height: 449px;
            }

        }
    }

    .item_con4 {
        .item_img_active {
            display: flex;
            justify-content: center;
            align-items: flex-start;

            .item_param {
                display: flex;
                justify-content: flex-start;
                flex-direction: column;
                align-items: flex-start;

                p {
                    margin-top: 50px;
                    color: #000000;
                    font-size: 30px;
                    margin-left: 90px;

                    span {
                        color: #808080;
                        margin-left: 40px;
                    }
                }
            }
        }
    }

    .item_con5 {
        width: 1150px;
        height: auto;
        overflow: hidden;
        margin: 0 auto;

        .item_h2 {
            width: 1150px;
            color: #242424;
            font-size: 0.3rem;
            margin: 0.5rem 0rem;
            margin-bottom: 0px;

        }

        .item_p {
            width: 1150px;
            margin-bottom: 0.8rem;
            height: auto;
            overflow: hidden;

            p {

                color: #000000;
                font-size: 30px;
                margin-top: 30px;
                padding-left: 270px;

                span {
                    color: #808080;
                    margin-left: 0.2rem;

                }
            }
        }

        .item_bottom {
            width: 1150px;
            height: 1px;
            background: rgba(144, 144, 144, 1);
            opacity: 0.5;
            margin: 0 auto;
            margin-bottom: 0.5rem;
            margin-top: 0.5rem;
        }
    }
}
</style>
