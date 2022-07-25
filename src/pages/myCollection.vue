<template>
    <div class="myCollection">
		<div class="notCollection">
			<image mode="aspectFill" src="../static/icon/取消收藏.png"></image>
			<div class="text">
				<span>暂无收藏专辑</span>
			</div>
			<div class="more">
				<span>去看看更多精彩内容</span>
			</div>
		</div>
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
                        <span>左右滑动切换节目</span>
                    </div>
                </div>
                <div class="broadcast">
                    <image src="../static/icon/24gf-pauseCircle.png"></image>
                </div>
                <div class="text">
                    <image src="../static/icon/文件.png"></image>
                </div>
            </div>
            <!-- 进度条 -->
            <div class="progressBar" @click.stop>
                <slider class="slider" min="0" max="100" value="5" activeColor="#D3AB58" block-size="12"></slider>
            </div>
        </div>
	</div>
</template>

<script>
export default {
    name:"myCollection",
	data() {
		return {
			property: 'value',
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
.myCollection{
	height: 100vh;
	width: 100vw;
	position: relative;
	.notCollection{
		height: 86vh;
		width: 100vw;
		display: flex;
		flex-flow: column nowrap;
		align-items: center;
		justify-content: center;
		font-size: 28rpx;
		image{
			height: 200rpx;
			width: 200rpx;
		}
		.text{
			color: gray;
		}
		.more{
			color: #D3AB58;
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
                    font-size: 30rpx;
                    font-weight: 600;
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