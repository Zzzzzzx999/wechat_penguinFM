<template>
    <div class="recentlyListened">
        <div class="addToSiri">
            <image src="../static/Picture_material/1657979583074.jpg"></image>
            <span>添加“播放最近收听”到Siri</span>
            <image id="right" src="../static/icon/homeIcon/右箭头.png"></image>
        </div>
        <div class="notRecentPrograms" v-if="recentProgram">
            <image src="../static/icon/Time-Folder.png"></image>
            <div class="recent">
                <span>暂无最近收听</span>
            </div>
            <div class="more">
                <span>去收听更多精彩节目</span>
            </div>
        </div>
        <div class="recentPrograms" v-if="!recentProgram">
            <div class="programs">
                <div class="programLeft">
                    <image mode="aspectFill" src="https://img2.baidu.com/it/u=1719968675,2457840328&fm=253&fmt=auto&app=138&f=JPEG?w=998&h=500"></image>
                </div>
                <div class="programRight">
                    <div class="programTitle">
                        <span>最近收听的节目</span>
                    </div>
                    <div class="programContent">
                        <span>共4集</span>
                    </div>
                </div>
            </div>
            <div class="programs">
                <div class="programLeft">
                    <image mode="aspectFill" src="https://i0.hdslb.com/bfs/music/3e0cfc04de84ce6176c18bb92394a1b5efa57978.jpg@370w_370h.webp"></image>
                </div>
                <div class="programRight">
                    <div class="programTitle">
                        <div class="boutique">
                            <span id="Title">独家</span>
                            <span id="Name">西汉盛世的启示</span>
                        </div>
                    </div>
                    <div class="programContent">
                        <span>上次听到: 62从婴儿囚犯到皇帝</span>
                    </div>
                    <div class="programDetail">
                        <span>侯杨方</span>
                    </div>
                </div>
            </div>
            <div class="programs">
                <div class="programLeft">
                    <image mode="aspectFill" src="https://fm-image-1251316161.file.myqcloud.com/fm/photo/album/rmid_album_360/q/6/0033BIbK1iywq6.jpg?time=1537845352"></image>
                </div>
                <div class="programRight">
                    <div class="programTitle">
                        <div class="boutique">
                            <span id="Title">自制</span>
                            <span id="Name">企小鹅经典儿歌100首</span>
                        </div>
                    </div>
                    <div class="programContent">
                        <span>上次听到: 001外婆桥</span>
                    </div>
                    <div class="programDetail">
                        <span>小企鹅爱儿歌</span>
                    </div>
                </div>
            </div>
            <div class="programs">
                <div class="programLeft">
                    <image mode="aspectFill" src="https://img.ting55.com/2018/08/12743.jpg!300"></image>
                </div>
                <div class="programRight">
                    <div class="programTitle">
                        <div class="boutique">
                            <span id="Title">精品</span>
                            <span id="Name">中国超恐怖鬼故事(灵姐姐播讲)</span>
                        </div>
                    </div>
                    <div class="programContent">
                        <span>上次听到: 001微信惊魂</span>
                    </div>
                    <div class="programDetail">
                        <span>鳄鱼书场</span>
                    </div>
                </div>
            </div>
            <div class="programs">
                <div class="programLeft">
                    <image mode="aspectFill" src="https://bkimg.cdn.bcebos.com/pic/d50735fae6cd7b8915c84450012442a7d8330eb8?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U5MzM=,g_7,xp_5,yp_5/format,f_auto"></image>
                </div>
                <div class="programRight">
                    <div class="programTitle">
                        <div class="boutique">
                            <span id="Title">热门</span>
                            <span id="Name">小月姐姐|儿童必听睡前故事情商熏陶</span>
                        </div>
                    </div>
                    <div class="programContent">
                        <span>上次听到: 小猪比比的水杯结冰了</span>
                    </div>
                    <div class="programDetail">
                        <span>小月姐姐</span>
                    </div>
                </div>
            </div>
        </div>
        <div class="everyoneIsListening">
            <div class="title">
                <span>大家都在听</span>
            </div>
            <div class="programs">
                <div class="programLeft">
                    <image mode="aspectFill" src="https://bkimg.cdn.bcebos.com/pic/d50735fae6cd7b8915c84450012442a7d8330eb8?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U5MzM=,g_7,xp_5,yp_5/format,f_auto"></image>
                </div>
                <div class="programRight">
                    <div class="programTitle">
                        <div class="boutique">
                            <span id="Title">精品</span>
                            <span id="Name">蕊希电台</span>
                        </div>
                    </div>
                    <div class="programContent">
                        <span>更新至:朋友圈三天可见，透露了你的社交观 原 【一个人听】...</span>
                    </div>
                    <div class="programDetail">
                        <span>9.7分 | 播放21.5亿 | 蕊希</span>
                    </div>
                </div>
            </div>
            <div class="programs">
                <div class="programLeft">
                    <image mode="aspectFill" src="https://fm-image-1251316161.file.myqcloud.com/fm/photo/album/rmid_album_360/R/i/003OiE121lHxRi.jpg?time=1555472621"></image>
                </div>
                <div class="programRight">
                    <div class="programTitle">
                        <div class="boutique">
                            <span id="Title">精品</span>
                            <span id="Name">最强打脸系统 (爆笑)</span>
                        </div>
                    </div>
                    <div class="programContent">
                        <span>更新至:第1512章，听谦讲故事，专治不开心！今年的笑点，我承包了，此书逗趣...</span>
                    </div>
                    <div class="programDetail">
                        <span>9.6分 | 播放21.5亿 | 谦儿2016</span>
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
    name:"recentlyListened",
    data() {
        return {
            recentProgram:false, //是否有最近收听节目
        }
    }
}
</script>

<style lang="less">
.recentlyListened{
    height: 100%;
    width: 100vw;
    position: relative;
    display: flex;
    flex-flow: column nowrap;
    background-color: whitesmoke;
    .addToSiri{
        background-color: white;
        height: 100rpx;
        padding: 0 40rpx;
        display: flex;
        align-items: center;
        image{
            width: 60rpx;
            height: 60rpx;
            min-height: 60rpx;
            min-width: 60rpx;
        }
        span{
            padding-left: 40rpx;
            flex-grow: 1;
        }
        #right{
            width: 37rpx;
            height: 37rpx;
            min-height: 37rpx;
            min-width: 37rpx;
        }
    }
    .notRecentPrograms{
        height: 540rpx;
        width: 100vw;
        display: flex;
        flex-flow: column nowrap;
        align-items: center;
        justify-content: center;
        font-size: 28rpx;
        image{
            height: 150rpx;
            width: 150rpx;
        }
        .recent{
            margin: 10rpx 0;
            color: gray;
        }
        .more{
            color: #D3AB58;
        }

    }
    .recentPrograms{
        margin: 40rpx 0;
    }
    .everyoneIsListening{
        display: flex;
        align-items: center;
        flex-flow: column nowrap;
        margin-bottom: 210rpx;
        .title{
            font-size: 42rpx;
            font-weight: 500;
            margin: 40rpx 0;
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
        z-index: 3;
        position: fixed;
        left: 0;
        top: 86vh;
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
// 节目
    .programs{
        display: flex;
        align-items: center;
        margin: 20rpx 40rpx;
        .programLeft{
            width: 29%;
            image{
                height: 180rpx;
                width: 180rpx;
                border-radius: 15rpx;
            }
        }
        .programRight{
            width: 71%;
            margin-left: 30rpx;
            display: flex;
            flex-flow: column nowrap;
            .programTitle{
                display: flex;
                flex-flow: row wrap;
                align-items: center;
                .boutique{
                    font-size: 28rpx;
                    color: black;
                    font-weight: 300;
                }
                .programName{
                    margin-left: 20rpx;
                    font-size: 35rpx;
                    font-weight: 500;
                }
                #Title{
                    font-size: 24rpx;
                    color: black;
                    border: 1rpx solid black;
                    border-radius: 8rpx;
                    font-weight: 300;
                    padding: 0 6rpx;
                }
                #Name{
                    margin-left: 20rpx;
                    font-size: 35rpx;
                    font-weight: 500;
                }
            }
            .programContent{
                font-size: 26rpx;
                margin: 15rpx 0;
                color: grey;
                overflow: hidden;
            }
            .programDetail{
                color: grey;
                font-size: 26rpx;
            }
        }
    }
}
</style>