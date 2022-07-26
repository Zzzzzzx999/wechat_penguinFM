<template>
	<div class="content">
		<div class="logo">
			<image src="../../static/Picture_material/qiE.jpg"></image>
			<div class="name">
				<span>企鹅FM</span>
			</div>
			<div class="detail">
				<span>最懂你的私人电台</span>
			</div>
		</div>
		<div class="login">
			<div class="loginMethods">
				<div class="qq loginItem" @click="login('../home?loginWay=qq')">
					<image src="../../static/icon/QQ.png"></image>
					<span>QQ登录</span>
				</div>
				<div class="wechat loginItem" @click="login('../home?loginWay=weixin')">
					<image src="../../static/icon/微信.png"></image>
					<span>微信登录</span>
				</div>
			</div>
			<div class="lookAround" @click="login('../home?loginWay=tourist')">
				<span>随便看看</span>
				<image src="../../static/icon/右箭头.png"></image>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			login(path){
				wx.navigateTo({url:path})
			}
		}
	}
</script>

<style lang="less">
	.content {
		height: 100vh;
		width: 100vw;
		background-color: #DBB76B;
		display: flex;
		flex-flow: column nowrap;
		align-items: center;
		justify-content: space-around;
		.logo{
			display: flex;
			flex-flow: column nowrap;
			justify-content: center;
			align-items: center;
			width: 375rpx;
			height: 550rpx;
			image{
				width: 350rpx;
				height: 350rpx;
			}
			.name{
				font-size: 90rpx;
				font-weight: 500;
				font-family: emoji;
				letter-spacing: 5rpx;
			}
			.detail{
				font-size: 33rpx;
				font-weight: 400;
				letter-spacing: 8rpx;
			}
		}
		.login{
			width: 630rpx;
			height: 250rpx;
			display: flex;
			flex-flow: column nowrap;
			justify-content: center;
			align-items: center;
			.loginMethods{
				height: 100%;
				width: 100%;
				display: flex;
				flex-flow: row nowrap;
				justify-content: space-around;
				align-items: center;
				.loginItem{
					height: 100rpx;
					width: 100%;
					width: 280rpx;
					border-radius: 30rpx;
					background-color: #8E7746;
					display: flex;
					align-items: center;
					justify-content: center;
					image{
						width: 50rpx;
						height: 50rpx;
						padding-right: 15rpx;
					}
					span{
						color: white;
					}
				}
			}
			.lookAround{
				height: 100%;
				width: 100%;
				display: flex;
				justify-content: center;
				align-items: center;
				image{
					height: 35rpx;
					width: 35rpx;
					padding-right: 15rpx;
				}
				span{
					color: white;
				}
			}
		}
	}

</style>
