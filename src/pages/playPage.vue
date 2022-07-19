<template>
    <div class="playPage">
        <div class="playtop">
            <image mode="aspectFill" src="https://img0.baidu.com/it/u=1303479120,3193737549&fm=253&fmt=auto&app=138&f=JPEG?w=689&h=500"></image>
            <div class="user">
                <div class="number">
                    <span>11</span>
                </div>
                <image mode="aspectFill" src="https://img2.baidu.com/it/u=263031947,1647848730&fm=253&fmt=auto&app=138&f=JPEG?w=501&h=500"></image>
                <image mode="aspectFill" src="https://img0.baidu.com/it/u=3365573645,2073973856&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"></image>
            </div>
            <div class="functionalArea">
                <image mode="aspectFill" src="../static/icon/礼物.png"></image>
                <image mode="aspectFill" src="../static/icon/消息.png"></image>
            </div>
        </div>
        <div class="playContent">
            <div class="progressBar" @click.stop>
                <slider class="slider" min="0" max="100" value="30" activeColor="#f1d498" block-color="#D3AB58" block-size="12"></slider>
                <div class="text">
                    <span>02:04</span>
                    <span>17:22</span>
                </div>
            </div>
            <div class="playService">
                <div class="playConfig">
                    <div class="definition configItem">
                        <span>高清</span>
                        <image src="../static/icon/选择器展开.png"></image>
                    </div>
                    <div class="speakingSpeed configItem">
                        <span>语速</span>
                        <image src="../static/icon/选择器展开.png"></image>
                    </div>
                    <div class="order configItem">
                        <span>顺序</span>
                        <image src="../static/icon/选择器展开.png"></image>
                    </div>
                </div>
                <div class="callSiri">
                    <image src="../static/Picture_material/1657979583074.jpg"></image>
                </div>
            </div>
            <div class="playControl">
                <image id="changeTime" src="../static/icon/后退-22.png"></image>
                <image id="cutSong" src="../static/icon/24gf-previousCircle.png"></image>
                <image id="play" src="../static/icon/24gf-pauseCircle.png"></image>
                <image id="cutSong" src="../static/icon/24gf-playCircle.png"></image>
                <image id="changeTime" src="../static/icon/前进-22.png"></image>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:"playPage",
    data() {
        return {
            property: 'value',
        };
    },
}
</script>

<style lang="less">
.playPage{
    height: 100vh;
    width: 100vw;
    .playtop{
        height: 53vh;
        width: 100vw;
        position: relative;
        image{
            height: 100%;
            width: 100%;
        }
        .user{
            height: 170rpx;
            width: 60rpx;
            position: absolute;
            top: 50%;
            right: 5%;
            transform: translate(0,-100%);
            display: flex;
            flex-flow: column nowrap;
            align-items: center;
            justify-content: space-around;
            .number{
                font-size: 25rpx;
                color: white;
            }
            image{
                height: 50rpx;
                width: 50rpx;
                border-radius: 50%;
            }
        }
        .functionalArea{
            height: 150rpx;
            width: 60rpx;
            position: absolute;
            top: 75%;
            right: 5%;
            transform: translate(0,-15%);
            display: flex;
            flex-flow: column nowrap;
            align-items: center;
            justify-content: space-around;
            image{
                height: 50rpx;
                width: 50rpx;
            }
        }
    }
    .playContent{
        height: 47vh;
        display: flex;
        flex-flow: column nowrap;
        .progressBar{
            height: 20rpx;
            width: 100vw;
            display: flex;
            flex-flow: column nowrap;
            justify-content: center;
            .slider{
                height: 35rpx;
                width: 100%;
                margin: 0;
                vertical-align: center;
            }
            .wx-slider-thumb {
                border-radius: 0;
            }
            .wx-slider-handle-wrapper{
                height: 20rpx;
            }
            .text{
                margin: 0 30rpx;
                display: flex;
                justify-content: space-between;
                color: rgb(160, 158, 158);
                font-size: 25rpx;
            }
        }
        .playService{
            padding-left: 50rpx;
            margin-top: 100rpx;
            height: 60rpx;
            display: flex;
            justify-content: center;
            align-items: center;
            .playConfig{
                flex-grow: 1;
                height: 60rpx;
                display: flex;
                justify-content: center;
                align-items: center;
                .configItem{
                    margin: 7rpx;
                    height: 35rpx;
                    width: 85rpx;
                    border: 2rpx solid gray;
                    border-radius: 20rpx;
                    font-size: 23rpx;
                    color: rgb(165, 164, 164);
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    image{
                        height: 25rpx;
                        width: 25rpx;
                    }
                }
            }
            .callSiri{
                height: 60rpx;
                width: 60rpx;
                border-bottom-left-radius: 30rpx;
                border-top-left-radius: 30rpx;
                display: flex;
                align-items: center;
                justify-content: center;
                padding-right: 10rpx;
                background-color: rgb(235, 221, 221);
                image{
                    width: 35rpx;
                    height: 35rpx;
                    border-radius: 50%;
                }
            }
        }
        .playControl{
            height: 150rpx;
            display: flex;
            justify-content: space-around;
            align-items: center;
            margin: 50rpx 30rpx;
            #changeTime{
                height: 50rpx;
                width: 50rpx;
            }
            #cutSong{
                height: 80rpx;
                width: 80rpx;
            }
            #play{
                height: 130rpx;
                width: 130rpx;
            }
        }
    }
}
</style>