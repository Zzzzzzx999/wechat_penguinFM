<template>
    <div class="recentlyListened">
        <div class="addToSiri">
            <image src="../static/Picture_material/1657979583074.jpg"></image>
            <span>添加“播放最近收听”到Siri</span>
            <image id="right" src="../static/icon/homeIcon/右箭头.png"></image>
        </div>
        <div class="recentPrograms">
            <image src="../static/icon/Time-Folder.png"></image>
            <div class="recent">
                <span>暂无最近收听</span>
            </div>
            <div class="more">
                <span>去收听更多精彩节目</span>
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
                            <span>精品</span>
                        </div>
                        <div class="programName">
                            <span>蕊希电台</span>
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
                    <image mode="aspectFill" src="https://bkimg.cdn.bcebos.com/pic/d50735fae6cd7b8915c84450012442a7d8330eb8?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U5MzM=,g_7,xp_5,yp_5/format,f_auto"></image>
                </div>
                <div class="programRight">
                    <div class="programTitle">
                        <div class="boutique">
                            <span>精品</span>
                        </div>
                        <div class="programName">
                            <span>最强打脸系统 (爆笑)</span>
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
    </div>
</template>

<script>
export default {
    name:"recentlyListened",
    data() {
        return {
            
        }
    },
}
</script>

<style lang="less">
.recentlyListened{
    height: 100vh;
    width: 100vw;
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
    .recentPrograms{
        height: 600rpx;
        width: 100vw;
        display: flex;
        flex-flow: column nowrap;
        align-items: center;
        justify-content: center;
        font-size: 30rpx;
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
    .everyoneIsListening{
        display: flex;
        align-items: center;
        flex-flow: column nowrap;
        .title{
            font-size: 42rpx;
            font-weight: 500;
            margin: 40rpx 0;
        }
        .programs{
            display: flex;
            align-items: center;
            margin: 20rpx 40rpx;
            .programLeft{
                width: 30%;
                image{
                    height: 200rpx;
                    width: 200rpx;
                    border-radius: 15rpx;
                }
            }
            .programRight{
                width: 70%;
                margin-left: 30rpx;
                display: flex;
                flex-flow: column nowrap;
                .programTitle{
                    display: flex;
                    align-items: center;
                    height: 50rpx;
                    .boutique{
                        font-size: 26rpx;
                        color: black;
                        border: 1rpx solid black;
                        border-radius: 8rpx;
                    }
                    .programName{
                        margin-left: 20rpx;
                        font-size: 35rpx;
                        font-weight: 500;
                    }
                }
                .programContent{
                    font-size: 24rpx;
                    margin: 15rpx 0;
                    color: grey;
                    overflow: hidden;
                }
                .programDetail{
                    color: grey;
                    font-size: 24rpx;
                }
            }
        }
    }
}
</style>