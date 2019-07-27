<template>
<div class="income">
    <headers></headers>
    <div class="income_con">
        <div class="banner">
            <div class="my_come_text">收益说明</div>

        </div>
        <div class="income_text">
            <div class="item_top">
                <div class="text">
                    <div class="h2">收益概述</div>
                    <div class="text_con">
                        西柚用户通过共享自身的资源（带宽和存储）给上游的企业来赚取收益，我们会统一通过西柚积分的形式进行收益发放。
                    </div>
                </div>
            </div>
            <div class="item_top_middle">
                <div class="item_h2">为什么会有收益？</div>
                <div class="item_p">
                    <p> 随着随着网络视频、在线直播、物联网、5G、人工智能等行业的爆发式增长，处于该行业的企业或者公司对带宽和存储的需求也是指数级增长，而专业运营商提供的带宽和存储由于价格和其他诸多因素并不能完全满足需求，另一方面大量普通互联网用户的带宽和存储资源并未充分利用而闲置下来。</p>

                    <p>而我们通过大量的西柚机将构建出一个全球性的分布式共享存储网络，西柚机就是桥接企业和西柚用户的物理纽带，将用户的闲置资源输出给需求企业，为企业节省的网络成本将返还到广大西柚用户手中实现共享的最终价值。</p>
                </div>
                <div class="item_img">
                    <img src="../../assets/images/pc_income_01.png" alt="">
                </div>
            </div>
        </div>
        <div class="income_text1">
            <div class="item_con">
                <div class="item_con_l">
                    <div class="h2">积分是什么？</div>
                    <div class="item_l" style=" text-indent: 60px;width: 520px;">西柚积分就是用户共享资源后的收益凭证。用户贡献闲置带宽和存储时均会产生西柚积分奖励。奖励计量基本遵循多劳多得原则，贡献越多，奖励越高。我们将根据用户的网络带宽、存储空间、在线时长等多方面来确定最终的积分数值，并根据用户在全网用户总贡献值中的占比分配积分。</div>
                </div>
                <div class="item_con_r">
                    <img src="../../assets/images/pc_income_02.png" alt="">
                </div>
            </div>
        </div>
        <div class="income_text2">
            <div class="item_con">
                <div class="item_con_r">
                    <img src="../../assets/images/pc_income_03.png" alt="">
                </div>
                <div class="item_con_l" style="margin-left: 120px;">
                    <div class="h2">积分用途</div>
                    <div class="item_l" style="width: 588px;text-indent: 60px;">用户的积分可通过我们西柚APP的专属兑换通道，在任何时间进行积分兑换。积分兑换可兑换实物或者直接提现，也可参与公司的积分活动、红包、抽奖、商城折扣等，并享受公司价值生态体系内的多种付费服务。目前公司搭建的闲置共享经济体系正在逐步完善，积分可兑换的价值也将更加丰富多样。</div>
                </div>

            </div>

        </div>
        <div class="income_text3">
            <div class="item_con">
                <div class="item_con_l">
                    <div class="h2">注意事项</div>
                    <div class="item_l" style=" text-indent: 50px;">西柚团队将会对设备及各测试点进行不间断扫描，一旦发现用户利用软件、硬件等相关漏洞，侵入、拦截、破坏、修改程序以及使用带有伪造、篡改相关功能信息的软/硬件，伪造上行带宽、闲置存储空间、在线时长、硬件能力等将会立刻将相关设备锁定或注销，用户将不可再获得积分。</div>
                </div>

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
        return {

        }
    },

    components: {
        headers: headers,
        footers: footers
    }

}
</script>

<style lang="less">
.income_con {
    width: 100%;
    height: auto;
    overflow: hidden;

    .banner {
        background: url(../../assets/images/myincome.png) no-repeat center;
        width: 100%;
        height: 676px;
        z-index: 10;
        display: flex;
        justify-content: center;
        align-items: center;
        .my_come_text{
            font-size: 90px;
            color: #000000;
            font-weight: 400;
        }
      
    }

    .income_text {
        height: auto;
        width: 100%;
        // background: #F9F9F9;

        .item_top {
            width: 1200px;
            height: 289px;
            background: #F9F9F9;
            box-shadow: 0px 4px 70px 0px rgba(40, 32, 25, 0.1);
            margin: 0 auto;
            overflow: hidden;
            margin-top: -120px;
            z-index: 10000;

            .h2 {
                color: #000000;
                font-size: 44px;
                margin-top: 50px;
            }

            .text {
                width: 1000px;
                height: auto;
                overflow: hidden;
                margin: 0 auto;

                .text_con {
                    color: #5C5C5C;
                    font-size: 30px;
                    margin-top: 40px;
                    line-height: 50px;
                }

            }
        }

        .item_top_middle {
            width: 1200px;
            height: auto;
            overflow: hidden;
            margin: 0 auto;
            text-align: center;
           // background: #F9F9F9;

            .item_h2 {
                color: #000000;
                font-size: 48px;
                margin-top: 140px;

            }

            .item_p {
                color: #3F3F3F;
                font-size: 30px;

                p {
                    margin-top: 50px;
                    line-height: 50px;
                }
            }

            .item_img {
                margin-top: 70px;
            }

        }
    }

    .income_text1 {
        width: 100%;
        height: auto;
        overflow: hidden;

        //  background: #ffffff;
        .item_con {
            width: 1200px;
            height: auto;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 180px;
            margin-bottom: 160px;

            .item_con_l {

                .h2 {
                    color: #000000;
                    font-size: 42px;
                }

                .item_l {
                    margin-top: 50px;
                    color: #808080;
                    font-size: 30px;
                }
            }
        }

    }

    .income_text2 {
        width: 100%;
        height: auto;
        overflow: hidden;
        background: #F9F9F9;

        .item_con {
            width: 1000px;
            height: auto;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 180px;
            margin-bottom: 160px;

            .item_con_l {
                margin-left: 150px;
                .h2 {
                    color: #000000;
                    font-size: 42px;
                }

                .item_l {
                    margin-top: 50px;
                    color: #808080;
                    font-size: 30px;
                }
            }
        }

    }
    .income_text3{
        width: 100%;
        height: 280px;
        background: #ffffff;
        .item_con{
            width: 1200px;
            height: auto;
            overflow: hidden;
            margin:0 auto;
            .h2{
                color: #000000;
                font-size: 30px;
                margin-top: 60px;

            }
            .item_l{
                color: #808080;
                font-size: 22px;
                margin-top: 20px;
            }
        }
    }
}
</style>
