<template>
    <div class="playPage">
        <div class="playtop" :class="{'playMask':adjustSpeed}">
            <image mode="aspectFill" src="https://img0.baidu.com/it/u=1303479120,3193737549&fm=253&fmt=auto&app=138&f=JPEG?w=689&h=500"></image>
            <div class="user">
                <div class="number">
                    <span>11</span>
                </div>
                <image mode="aspectFill" src="https://img2.baidu.com/it/u=263031947,1647848730&fm=253&fmt=auto&app=138&f=JPEG?w=501&h=500"></image>
                <image mode="aspectFill" src="https://img0.baidu.com/it/u=3365573645,2073973856&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"></image>
            </div>
            <div class="functionalArea">
                <image mode="aspectFill" src="../static/icon/礼物.png" @click="changePath('../pages/gift')"></image>
                <image mode="aspectFill" src="../static/icon/消息.png"></image>
            </div>
        </div>
        <div class="playContent" :class="{'playMask':adjustSpeed}">
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
                    <div class="speakingSpeed configItem" @click="adjustSpeed=true">
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
            <div class="programControl">
                <image :src="collect?'../static/icon/playPage/取消收藏.png':'../static/icon/playPage/取消收藏(1).png'" @click="collect=!collect"></image>
                <image src="../static/icon/playPage/排序.png"></image>
                <image src="../static/icon/playPage/转发.png"></image>
                <image :src="timing?'../static/icon/playPage/广播-定时(1).png':'../static/icon/playPage/广播-定时.png'" @click="timing=!timing"></image>
                <image src="../static/icon/playPage/文本.png"></image>
            </div>
        </div>
        <div class="playPageTitle">
            <span>62从婴儿囚犯到皇帝</span>
        </div>
        <div class="adjustSpeed" v-if="adjustSpeed">
           <div class="speed">
                 <div class="adjustTop">
                    <div class="title">
                        <span>调整语速</span>
                    </div>
                    <div class="progressBar">
                        <div class="speedDetail">
                            <div class="speedbox" :class="{'boxHidden':speed.one}">
                                <span>0.5x</span>
                            </div>
                            <div class="speedbox" :class="{'boxHidden':speed.two}">
                                <span>1.0x</span>
                            </div>
                            <div class="speedbox" :class="{'boxHidden':speed.three}">
                                <span>1.5x</span>
                            </div>
                            <div class="speedbox" :class="{'boxHidden':speed.four}">
                                <span>2.0x</span>
                            </div>
                        </div>
                        <slider class="slider" min="0" max="90" model:value="sliderValue" 
                            activeColor="rgb(173, 169, 169)" block-color="#D3AB58" block-size="12" backgroundColor="rgb(173, 169, 169)"
                            @change="changeSpeed">
                            <div class="box">
                                <div class="boxes"></div>
                                <div class="boxes"></div>
                                <div class="boxes"></div>
                            </div>
                        </slider>
                        
                        <div class="sliderTime">
                            <span>0.5x</span>
                            <span>1.0x</span>
                            <span>1.5x</span>
                            <span>2.0x</span>
                        </div>
                    </div>
                </div>
                <div class="determine">
                    <span @click="adjustSpeed=false">确定</span>
                </div>
           </div>
        </div>
    </div>
</template>

<script>
export default {
    name:"playPage",
    data() {
        return {
            collect: false,     //收藏
            timing:false,    //定时闹钟
            adjustSpeed:false,    //调整语速
            sliderValue:30,     //滑块的值
            speed:{
                one:true,
                two:false,
                three:true,
                four:true,
            }
        };
    },
    methods: {
        changePath(path){
            wx.redirectTo({url:path})
        },
        changeSpeed(e){
            console.log(e.detail.value);
            if (e.detail.value<15) {
                this.sliderValue = 0
                this.speedGetTrue()
                this.speed.one=false
            }else if(e.detail.value>15 && e.detail.value<45){
                this.sliderValue = 30
                this.speedGetTrue()
                this.speed.two=false
            }else if(e.detail.value>45 && e.detail.value<75){
                this.sliderValue = 60
                this.speedGetTrue()
                this.speed.three=false
            }else{
                this.sliderValuel = 90
                this.speedGetTrue()
                this.speed.four=false
            }
            console.log(this.sliderValue);
        },
        speedGetTrue(){
            this.speed.one=true
            this.speed.two=true
            this.speed.three=true
            this.speed.four=true
        }
    }
}
</script>

<style lang="less">
.playMask{
    // background-color: rgba(0, 0, 0, .3);
}
.playPage{
    height: 100vh;
    width: 100vw;
    position: relative;
    .playtop{
        height: 53vh;
        width: 100vw;
        position: relative;
        image{
            height: 100%;
            width: 100%;
            filter: brightness(80%);
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
            margin: 80rpx 30rpx;
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
        .programControl{
            margin: 50rpx 13rpx 0;
            display: flex;
            justify-content: space-around;
            align-items: center;
            image{
                height: 55rpx;
                width: 55rpx;
            }
        }
    }
    .adjustSpeed{
        position: fixed;
        top: 0;
        left: 0;
        height: 100vh;
        width: 100vw;
        display: flex;
        align-items: flex-end;
		background: rgba(0, 0, 0, 0.45);
        z-index: 7;
        .speed{
            height: 30vh;
            width: 100vw;
            display: flex;
            flex-flow: column nowrap;
            align-items: center;
            background: rgb(221, 220, 220);
            z-index: 8;
            .adjustTop{
                height: 62%;
                width: 100vw;
                background-color: white;
                display: flex;
                flex-flow: column nowrap;
                align-items: center;
                .title{
                    height: 100rpx;
                    width: 100%;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    font-size: 28rpx;
                    color: rgb(165, 164, 164);
                }
                .progressBar{
                    height: 30rpx;
                    width: 90vw;
                    display: flex;
                    flex-flow: column nowrap;
                    justify-content: center;
                    align-items: center;
                    margin-top: 50rpx;
                    .speedDetail{
                        display: flex;
                        justify-content: space-between;
                        width: 100vw;
                        padding: 0 20rpx;
                        box-sizing: border-box;
                        .speedbox{
                            height: 60rpx;
                            width: 90rpx;
                            background-color: rgba(243, 233, 233, 0.849);
                            border-radius: 20rpx;
                            margin-bottom: 20rpx;
                            color: #e0ac42;
                            display: flex;
                            justify-content: center;
                            align-items: center;
                        }
                        .boxHidden{
                            visibility:hidden;
                        }
                    }
                    .slider{
                        width: 95%;
                        margin: 0;
                        vertical-align: center;
                        position: relative;
                        .box{
                            position: absolute;
                            top: 8rpx;
                            left: 3rpx;
                            height: 10rpx;
                            width:100%;
                            display: flex;
                            justify-content: space-between;
                            .boxes{
                                height: 16rpx;
                                width: 33.33%;
                                border-left: 3rpx solid rgb(173, 169, 169);
                                z-index: -5;
                            }
                            .boxes:last-child{
                                border-right: 3rpx solid rgb(173, 169, 169);
                            }
                        }
                    }
                    .wx-slider-thumb {
                        // display: none;
                    }
                    .sliderTime{
                        display: flex;
                        width: 100%;
                        justify-content: space-between;
                        font-size: 20rpx;
                        padding: 0 10rpx;
                        color: grey;
                    }
                }
            }
        }
        .determine{
            flex-grow: 1;
            width: 100vw;
            display: flex;
            align-content: center;
            justify-content: center;
            background-color: white;
            margin-top: 20rpx;
            span{
                font-size: 35rpx;
                font-weight: 500;
                margin-top: 30rpx;
            }
        }
        
    }
    .playPageTitle{
        position: absolute;
        top: 50rpx;
        left: 30rpx;
        color: aliceblue;
        font-size: 42rpx;
        font-weight: 500;
        z-index: 6;
    }
}
</style>