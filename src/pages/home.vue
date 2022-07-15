<template>
    <div class="home">
        <div class="top">
            <div class="search">
                <image src="../static/icon/search.png"></image>
            </div>
            <div class="regions">
                <span>精品</span>
                <span>分类</span>
                <span class="select">我的</span>
            </div>
            <div class="history">
                <image src="../static/icon/countdown.png"></image>
            </div>
        </div>
        <div class="content">
            <div class="myInfo" @click="changePath('./myPage')">
                <div class="headSculpture">
                    <div class="userHeadSculpture">
                        <image src="https://img1.baidu.com/it/u=2145784900,2865107303&fm=253&fmt=auto&app=138&f=JPG?w=500&h=500"></image>
                        <image id="wechat" src="../static/icon/homeIcon/微信.png"></image>
                    </div>
                </div>
                <div class="infoDetail">
                    <div class="infoDetailTop">
                        <div class="name">
                            <span>小编</span>
                            <div class="grade">
                                <span>LV1</span>
                            </div>
                        </div>
                        <div class="recording" @click.stop>
                            <image src="../static/icon/麦克风.png"></image>
                            <span>录制</span>
                        </div>
                    </div>
                    <div class="infoDetailBottom">
                        <div class="works bottomItem">
                            <span>0</span>
                            <span id="infoType">作品</span>
                        </div>
                        <div class="follow bottomItem">
                            <span>0</span>
                            <span id="infoType">关注</span>
                        </div>
                        <div class="fans bottomItem">
                            <span>0</span>
                            <span id="infoType">粉丝</span>
                        </div>
                    </div>
                </div>
            </div>
            <div class="functionalDomain">
                <div class="areasMy">
                    <div class="functionalItem">
                        <div class="functionalItemLeft">
                            <image src="../static/icon/homeIcon/time_fill.png"></image>
                            <span>最近收听</span>
                        </div>
                        <div class="functionalItemRight">
                            <image id="rightArrow" src="../static/icon/homeIcon/右箭头.png"></image>
                        </div>
                    </div>
                    <div class="functionalItem">
                        <div class="functionalItemLeft">
                            <image src="../static/icon/homeIcon/square_check_fill.png"></image>
                            <span>我的下载</span>
                        </div>
                        <div class="functionalItemRight">
                            <image id="rightArrow" src="../static/icon/homeIcon/右箭头.png"></image>
                        </div>
                    </div>
                    <div class="functionalItem">
                        <div class="functionalItemLeft">
                            <image src="../static/icon/homeIcon/favor_fill_light.png"></image>
                            <span>我的收藏</span>
                        </div>
                        <div class="functionalItemRight">
                            <image id="rightArrow" src="../static/icon/homeIcon/右箭头.png"></image>
                        </div>
                    </div>
                    <div class="functionalItem">
                        <div class="functionalItemLeft">
                            <image src="../static/icon/homeIcon/cart_fill.png"></image>
                            <span>我的已购</span>
                        </div>
                        <div class="functionalItemRight">
                            <image id="rightArrow" src="../static/icon/homeIcon/右箭头.png"></image>
                        </div>
                    </div>
                    <div class="functionalItem" @click="changePath('./myWallet')">
                        <div class="functionalItemLeft">
                            <image src="../static/icon/homeIcon/money_bag_fill.png"></image>
                            <span>我的钱包</span>
                        </div>
                        <div class="functionalItemRight">
                            <image id="rightArrow" src="../static/icon/homeIcon/右箭头.png"></image>
                        </div>
                    </div>
                </div>
                <div class="areasCentre">
                    <div class="functionalItem">
                        <div class="functionalItemLeft">
                            <image src="../static/icon/homeIcon/home_fill.png"></image>
                            <span>活动中心</span>
                        </div>
                        <div class="functionalItemRight">
                            <image id="rightArrow" src="../static/icon/homeIcon/右箭头.png"></image>
                        </div>
                    </div>
                    <div class="functionalItem">
                        <div class="functionalItemLeft">
                            <image src="../static/icon/homeIcon/comment_fill.png"></image>
                            <span>消息中心</span>
                        </div>
                        <div class="functionalItemRight">
                            <image id="rightArrow" src="../static/icon/homeIcon/右箭头.png"></image>
                        </div>
                    </div>
                </div>
                <div class="areasListen">
                    <div class="functionalItem" @click="changePath('./runningListening')">
                        <div class="functionalItemLeft">
                            <image src="../static/icon/homeIcon/activity_fill.png"></image>
                            <span>跑步听</span>
                        </div>
                        <div class="functionalItemRight">
                            <image id="rightArrow" src="../static/icon/homeIcon/右箭头.png"></image>
                        </div>
                    </div>
                    <div class="functionalItem">
                        <div class="functionalItemLeft">
                            <image src="../static/icon/homeIcon/Wifi.png"></image>
                            <span>免流量收听</span>
                        </div>
                        <div class="functionalItemRight">
                            <span>未开通</span>
                            <image id="rightArrow" src="../static/icon/homeIcon/右箭头.png"></image>
                        </div>
                    </div>
                    <div class="functionalItem" @click="changePath('./setting')">
                        <div class="functionalItemLeft">
                            <image src="../static/icon/homeIcon/selection_fill.png"></image>
                            <span>设置</span>
                        </div>
                        <div class="functionalItemRight">
                            <image id="rightArrow" src="../static/icon/homeIcon/右箭头.png"></image>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="footer" @click="goPlayer()">
            <div class="playBar">
                <div class="radioAvatar">
                    <image src="../static/Picture_material/1657765591270.jpg"></image>
                </div>
                <div class="radioContent">
                    <div class="radioContentHeader">
                        <span>企鹅FM</span>
                    </div>
                    <div class="radioContentFooter">
                        <span>随心一按 听点有趣</span>
                    </div>
                </div>
                <div class="broadcast">
                    <image src="../static/icon/homeIcon/24gf-playCircle.png"></image>
                </div>
                <div class="text">
                    <image src="../static/icon/homeIcon/文件.png"></image>
                </div>
            </div>
            <!-- 进度条 -->
            <div class="progressBar" @click.stop>
                <slider class="slider" min="0" max="100" value="30" activeColor="#D3AB58" block-size="12"></slider>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'home',
    data() {
        return {
            
        }
    },
    methods: {
        changePath(path){
            wx.redirectTo({url:path})
        }
        /* goPlayer(){
            const backgroundAudioManager = wx.getBackgroundAudioManager()
            backgroundAudioManager.title =  '西汉盛世的启示'
            backgroundAudioManager.singer = '侯杨方'
            backgroundAudioManager.src = 'http://music.163.com/song/media/outer/url?id=447925558.mp3'
            backgroundAudioManager.coverImgUrl = 'https://i0.hdslb.com/bfs/music/3e0cfc04de84ce6176c18bb92394a1b5efa57978.jpg@370w_370h.webp'
        } */
    },
}
</script>

<style lang="less">
.home{
    background-color: #F9F9F9;
    height: 100vh;
    width: 100vw;
    display: flex;
    flex-flow: column nowrap;
    .top{
        height: 75rpx;
        width: 100vw;
        display: flex;
        flex-flow: row nowrap;
        justify-content: space-between;
        align-items: center;
        .search{
            padding-left: 30rpx;
            height: 50rpx;
            width: 50rpx;
            image{
                height: 100%;
                width: 100%;
            }
        }
        .regions{
            height: 100%;
            flex-grow: 1;
            padding: 0 100rpx;
            display: flex;
            justify-content: space-around;
            align-items: center;
            font-size: 38rpx;
            color: rgba(77, 76, 76, 0.705);
            .select{
                color: black;
            }
        }
        .history{
            padding-right: 30rpx;
            height: 50rpx;
            width: 50rpx;
            image{
                height: 100%;
                width: 100%;
            }
        }
    }
    .content{
        flex: 1;
        .myInfo{
            padding: 0 30rpx;
            height: 250rpx;
            width: 100vw;
            box-sizing: border-box;
            display: flex;
            align-items: center;
            .headSculpture{
                width: 25%;
                height: 200rpx;
                display: flex;
                justify-content: flex-start;
                align-items: center;
                .userHeadSculpture{
                    position: relative;
                    image{
                        height: 125rpx;
                        width: 125rpx;
                        border-radius: 50%;
                        z-index: 1;
                    }
                    #wechat{
                        height: 33rpx;
                        width: 33rpx;
                        position: absolute;
                        bottom: 2rpx;
                        right: -7rpx;
                        z-index: 2;
                    }
                }
            }
            .infoDetail{
                width: 75%;
                height: 200rpx;
                display: flex;
                flex-flow: column nowrap;
                justify-content: space-between;
                .infoDetailTop{
                    height: 45%;
                    width: 100%;
                    display: flex;
                    justify-content: space-between;
                    align-items: center;
                    .name{
                        height: 50rpx;
                        font-size: 43rpx;
                        font-weight: 400;
                        position: relative;
                        .grade{
                            width: 50rpx;
                            height: 25rpx;
                            font-size: 20rpx;
                            font-weight: 600;
                            position: absolute;
                            top: 0;
                            left: 90rpx;
                            background-color: #D3AB58;
                            display: flex;
                            justify-content: center;
                            align-items: center;
                        }
                    }
                    .recording{
                        width: 150rpx;
                        height: 50rpx;
                        border: 5rpx solid #D3AB58;
                        border-radius: 70rpx;
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        image{
                            height: 37rpx;
                            width: 37rpx;
                            padding-right: 10rpx;
                        }
                        span{
                            color: #D3AB58;
                            font-size: 30rpx;
                        }
                    }
                }
                .infoDetailBottom{
                    height: 55%;
                    display: flex;
                    justify-content: space-between;
                    .bottomItem{
                        width: 33%;
                        display: flex;
                        flex-flow: column nowrap;;
                        font-weight: 600;
                        font-size: 35rpx;
                        #infoType{
                            font-size: 28rpx;
                            font-weight: 400;
                            color: gray;
                        }
                    }
                }
            }
        }
        .functionalDomain{
            padding: 0 30rpx;
            box-sizing: border-box;
            display: flex;
            flex-flow: column nowrap;
            justify-content: space-between;
            .areasMy{
                display: flex;
                flex-flow: column nowrap;
                width: 100%;
                border-bottom: 1rpx solid #dfdfdf;
                padding-bottom: 35rpx;
            }
            .areasCentre{
                display: flex;
                flex-flow: column nowrap;
                width: 100%;
                border-bottom: 1rpx solid #dfdfdf;
                padding: 35rpx 0;
            }
            .areasListen{
                display: flex;
                flex-flow: column nowrap;
                width: 100%;
                padding: 35rpx 0;
            }
            .functionalItem{
                height: 75rpx;
                width: 100%;
                display: flex;
                align-items: center;
                .functionalItemLeft{
                    width: 50%;
                    height: 100%;
                    display: flex;
                    align-items: center;
                    image{
                        width: 50rpx;
                        height: 50rpx;
                        min-width: 50rpx;
                        min-height: 50rpx;
                        margin-right: 36rpx;
                    }
                    span{
                        font-size: 34rpx;
                    }
                }
                .functionalItemRight{
                    width: 50%;
                    display: flex;
                    justify-content: flex-end;
                    align-items: center;
                    span{
                        color: #c0bfbf;
                        font-size: 32rpx;
                        padding: 0 17rpx;
                    }
                    #rightArrow{
                        width: 30rpx;
                        height: 30rpx;
                    }
                }
                
            }
        }
    }
    .footer{
        width: 100vw;
        height: 210rpx;
        padding: 15rpx 0 60rpx;
        box-sizing: border-box;
        display: flex;
        flex-flow: column nowrap;
        align-items: center;
        background-color: #F9F9F9;
        .playBar{
            width: 100%;
            height: 130rpx;
            padding: 0 30rpx;
            box-sizing: border-box;
            display: flex;
            align-items: center;
            .radioAvatar{
                image{
                    width: 100rpx;
                    height: 100rpx;
                    min-width: 100rpx;
                    min-height: 100rpx;
                    border-radius: 10rpx;
                }
            }
            .radioContent{
                height: 75%;
                display: flex;
                flex-flow: column nowrap;
                justify-content: space-around;
                flex-grow: 1;
                padding: 0 20rpx;
                .radioContentHeader{
                    font-size: 36rpx;
                    font-weight: 500;
                }
                .radioContentFooter{
                    font-size: 28rpx;
                    color: #D3AB58;
                    background-clip: text;
                    // -webkit-text-fill-color: #e7dabe;
                    // -webkit-animation: slideShine 5s infinite;
                }
            }
            .broadcast{
                padding-right: 40rpx;
                image{
                    width: 65rpx;
                    height: 65rpx;
                    min-width: 65rpx;
                    min-height: 65rpx;
                }
            }
            .text{
                image{
                    width: 65rpx;
                    height: 65rpx;
                    min-width: 65rpx;
                    min-height: 65rpx;
                }
            }
        }
        .progressBar{
            height: 30rpx;
            width: 100vw;
            display: flex;
            align-items: center;
            .slider{
                width: 100%;
                margin: 0;
                vertical-align: center;
            }
            .wx-slider-thumb {
                display: none;
            }
        }
        
    }
}
</style>