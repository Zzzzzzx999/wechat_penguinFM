<template>
    <div class="footer" @click="goPlayer()">
        <div class="playBar">
            <div class="radioAvatar">
                <image mode="aspectFill" src="https://img0.baidu.com/it/u=1303479120,3193737549&fm=253&fmt=auto&app=138&f=JPEG?w=689&h=500"></image>
            </div>
            <div class="radioContent">
                <div class="radioContentHeader">
                    <span>62从婴儿囚犯到皇帝</span>
                </div>
                <div class="radioContentFooter">
                    <span>左右滑动 切换节目</span>
                </div>
            </div>
            <div class="broadcast" @click.stop>
                <image mode="aspectFill" @click="IsBroadcast=!IsBroadcast" :src="IsBroadcast?'../../static/icon/24gf-pauseCircle.png':'../../static/icon/24gf-playCircle.png'"></image>
            </div>
            <div class="text" @click.stop>
                <image mode="aspectFill" @click="IsText=!IsText" :src="IsText?'../../static/icon/文件.png':'../../static/icon/homeIcon/文件.png'"></image>
            </div>
        </div>
        <!-- 进度条 -->
        <div class="progressBar" @click.stop>
            <slider class="slider" min="0" max="100" value="30" activeColor="#D3AB58" block-size="12"></slider>
        </div>
    </div>
</template>

<script>
export default {
    name:'player',
    data() {
        return {
            IsBroadcast: false, //是否正在播放
            IsText: false, //是否显示文本
        };
    },
    methods: {
        goPlayer(){
            // const backgroundAudioManager = wx.getBackgroundAudioManager()
            // backgroundAudioManager.title =  '西汉盛世的启示'
            // backgroundAudioManager.singer = '侯杨方'
            // backgroundAudioManager.src = 'http://music.163.com/song/media/outer/url?id=447925558.mp3'
            // backgroundAudioManager.coverImgUrl = 'https://i0.hdslb.com/bfs/music/3e0cfc04de84ce6176c18bb92394a1b5efa57978.jpg@370w_370h.webp'
            wx.navigateTo({url:'../pages/playPage'})
        }
    }
}
</script>

<style lang="less">
.wx-slider-thumb {
    display: none;
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
                width: 75rpx;
                height: 75rpx;
                min-width: 75rpx;
                min-height: 75rpx;
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
                font-size: 27rpx;
                font-weight: 600;
            }
            .radioContentFooter{
                font-size: 23rpx;
                color: #D3AB58;
                background-clip: text;
                // -webkit-text-fill-color: #e7dabe;
                // -webkit-animation: slideShine 5s infinite;
            }
        }
        .broadcast{
            padding-right: 40rpx;
            image{
                width:50rpx;
                height: 50rpx;
                min-width: 50rpx;
                min-height: 50rpx;
            }
        }
        .text{
            image{
                width: 50rpx;
                height: 50rpx;
                min-width: 50rpx;
                min-height: 50rpx;
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
</style>