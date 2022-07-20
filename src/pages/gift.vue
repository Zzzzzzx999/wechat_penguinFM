<template>
    <div class="gift">
		<div class="totalGifts">
			<div class="playImage">
				<image mode="aspectFill" src="https://img0.baidu.com/it/u=1303479120,3193737549&fm=253&fmt=auto&app=138&f=JPEG?w=689&h=500"></image>
			</div>
			<div class="playContent">
				<div class="contentTop">
					<span>62从婴儿囚犯到皇帝</span>
				</div>
				<div class="contentBottom">
					<span>《西汉盛世的启示》 杨侯方</span>
				</div>
			</div>
			<div class="giftDetail">
				<image src="../static/icon/金豆，银豆-01.png"></image>
				<span>11</span>
			</div>
		</div>
		<div class="giftContent">
			<div class="giftItem">
				<div class="itemLeft">
					<span>1</span>
				</div>
				<div class="itemContent">
					<div class="userImage">
						<image src="https://img0.baidu.com/it/u=1955800537,184107213&fm=253&fmt=auto&app=120&f=JPEG?w=640&h=640"></image>
					</div>
					<div class="userInfo">
						<div class="userName">
							<span>时钟波动</span>
						</div>
						<div class="userContribution">
							<span>贡献了9朵免费玫瑰</span>
						</div>
					</div>
				</div>
				<div class="itemRight">
					<span>9</span>
				</div>
			</div>
			<div class="giftItem">
				<div class="itemLeft">
					<span>2</span>
				</div>
				<div class="itemContent">
					<div class="userImage">
						<image src="https://img2.baidu.com/it/u=824084087,458235982&fm=253&fmt=auto?w=400&h=400"></image>
					</div>
					<div class="userInfo">
						<div class="userName">
							<span>ice</span>
						</div>
						<div class="userContribution">
							<span>贡献了2朵免费玫瑰</span>
						</div>
					</div>
				</div>
				<div class="itemRight">
					<span>2</span>
				</div>
			</div>
		</div>
		<div class="giftGiving">
			<div class="myGift">
				<div class="itemLeft">
					<span>-</span>
				</div>
				<div class="itemContent">
					<div class="userImage">
						<image src="https://img0.baidu.com/it/u=1955800537,184107213&fm=253&fmt=auto&app=120&f=JPEG?w=640&h=640"></image>
					</div>
					<div class="userInfo">
						<div class="userContribution">
							<span>你还没有送出礼物</span>
						</div>
					</div>
				</div>
				<div class="itemRight" @click="giftGiving=true">
					<span>去送礼</span>
					<image src="../static/icon/playPage/右箭头.png"></image>
				</div>
			</div>
		</div>
		<div class="giving" v-if="giftGiving">
			<div class="rewardTitle">
				<div class="rewardTop">
					<div class="text">
						<span>打赏送礼</span>
					</div>
					<image src="../static/icon/关闭.png" @click="giftGiving=false"></image>
				</div>
				<div class="rewardContent">
					<div class="rewardItem" :class="{'activeItem':reward.a}" @click="changeReward(reward.a)">
						<div class="rewardImage">
							<image mode="aspectFill" src="https://img1.baidu.com/it/u=2007431631,2758384144&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=400"></image>
						</div>
						<div class="rewardPay">
							<span>免费</span>
							<span id="changePrice">(1金豆)</span>
						</div>
					</div>
					<div class="rewardItem" :class="{'activeItem':reward.b}">
						<div class="rewardImage">
							<image mode="aspectFill" src="https://img1.baidu.com/it/u=1790814123,4215139779&fm=253&fmt=auto&app=138&f=JPEG?w=507&h=500"></image>
						</div>
						<div class="rewardPay">
							<span>10金豆</span>
						</div>
					</div>
					<div class="rewardItem" :class="{'activeItem':reward.c}">
						<div class="rewardImage">
							<image mode="aspectFill" src="http://p6.itc.cn/images03/20200528/693f0c0ab85e4b6e9d26650ec3e25ef9.jpeg"></image>
						</div>
						<div class="rewardPay">
							<span>15金豆</span>
						</div>
					</div>
					<div class="rewardItem" :class="{'activeItem':reward.d}">
						<div class="rewardImage">
							<image mode="aspectFill" src="https://img0.baidu.com/it/u=2562872668,3341926168&fm=253&fmt=auto&app=138&f=JPG?w=1000&h=425"></image>
						</div>
						<div class="rewardPay">
							<span>666金豆</span>
						</div>
					</div>
					<div class="rewardItem" :class="{'activeItem':reward.e}">
						<div class="rewardImage">
							<image mode="aspectFill" src="https://img0.baidu.com/it/u=2280491051,3823646384&fm=253&fmt=auto&app=138&f=JPEG?w=300&h=225"></image>
						</div>
						<div class="rewardPay">
							<span>666金豆</span>
						</div>
					</div>
					<div class="rewardItem" :class="{'activeItem':reward.f}">
						<div class="rewardImage">
							<image mode="aspectFill" src="https://img2.baidu.com/it/u=3005909461,33718405&fm=253&fmt=auto&app=138&f=JPEG?w=400&h=400"></image>
						</div>
						<div class="rewardPay">
							<span>520金豆</span>
						</div>
					</div>
					<div class="rewardItem" :class="{'activeItem':reward.g}">
						<div class="rewardImage">
							<image mode="aspectFill" src="https://img1.baidu.com/it/u=1931175622,1598938568&fm=253&fmt=auto&app=138&f=JPEG?w=610&h=400"></image>
						</div>
						<div class="rewardPay">
							<span>16金豆</span>
						</div>
					</div>
					<div class="rewardItem" :class="{'activeItem':reward.h}">
						<div class="rewardImage">
							<image mode="aspectFill" src="https://img2.baidu.com/it/u=1228884032,780487984&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"></image>
						</div>
						<div class="rewardPay">
							<span>66金豆</span>
						</div>
					</div>
				</div>
				<div class="rewardQuantity">
					<div class="quantityItem" :class="{'activeQuantity':quantity.one}" @click="changeQuantity1">
						<span>1个</span>
					</div>
					<div class="quantityItem" :class="{'activeQuantity':quantity.two}" @click="changeQuantity2">
						<span>9个</span>
					</div>
					<div class="quantityItem" :class="{'activeQuantity':quantity.three}" @click="changeQuantity3">
						<span>99个</span>
					</div>
					<div class="quantityItem" :class="{'activeQuantity':quantity.four}" @click="changeQuantity4">
						<span>520个</span>
					</div>
					<div class="quantityItem" :class="{'activeQuantity':quantity.five}" @click="changeQuantity5">
						<span>1314个</span>
					</div>
				</div>
				<div class="choose">
					<button id="recharge">充值<span>(剩余金豆0)</span></button>
					<button id="give">赠送</button>
				</div>
			</div>
		</div>
    </div>
</template>

<script>
export default {
    name:'gift',
	data() {
		return {
			giftGiving: true,
			reward:{
				a:true,
				b:false,
				c:false,
				d:false,
				e:false,
				f:false,
				g:false,
				h:false,
			},
			quantity:{
				one:true,
				two:false,
				three:false,
				four:false,
				five:false
			}
		};
	},
	methods: {
		changeAllQuantity(){
			for(let i in this.quantity){
				this.quantity[i]=false
			}
		},
		changeQuantity1(){
			this.changeAllQuantity()
			this.quantity.one=true
		},
		changeQuantity2(){
			this.changeAllQuantity()
			this.quantity.two=true
		},
		changeQuantity3(){
			this.changeAllQuantity()
			this.quantity.three=true
		},
		changeQuantity4(){
			this.changeAllQuantity()
			this.quantity.four=true
		},
		changeQuantity5(){
			this.changeAllQuantity()
			this.quantity.five=true
		},
		changeReward(x){
			for(let i in this.reward){
				this.reward[i]=false
			}
			// this.reward.x=true
			
		}
	}
}
</script>

<style lang="less">
.gift{
	display: flex;
	flex-flow: column nowrap;
	position: relative;
	.totalGifts{
		display: flex;
		align-items: center;
		height: 120rpx;
		background-color: rgb(122, 119, 115);
		padding: 0 30rpx;
		.playImage{
			height: 75rpx;
			width: 75rpx;
			image{
				width: 75rpx;
				height: 75rpx;
				min-width: 75rpx;
				min-height: 75rpx;
				border-radius: 10rpx;
			}
		}
		.playContent{
			flex-grow: 1;
			display: flex;
			flex-flow: column nowrap;
			justify-content: space-around;
			padding-left: 20rpx;
			.contentTop{
				font-size: 29rpx;
				color: whitesmoke;
			}
			.contentBottom{
				font-size: 25rpx;
				color: rgb(179, 172, 172);
			}
		}
		.giftDetail{
			width: 75rpx;
			display: flex;
			flex-flow: column nowrap;
			align-items: center;
			image{
				height: 45rpx;
				width: 45rpx;
			}
			span{
				font-size: 25rpx;
				color: whitesmoke;
			}
		}
	}
	.giftContent{
		display: flex;
		flex-flow: column nowrap;
		.giftItem{
			height: 110rpx;
			width: 100vw;
			display: flex;
			align-items: center;
			padding: 0 30rpx;
			box-sizing: border-box;
			.itemLeft{
				width: 50rpx;
				height: 100%;
				color: #D3AB58;
				display: flex;
				justify-content: center;
				align-items: center;
			}
			.itemContent{
				flex-grow: 1;
				height: 100%;
				display: flex;
				align-items: center;
				padding-left: 20rpx;
				.userImage{
					width: 75rpx;
					height: 75rpx;
					image{
						width: 75rpx;
						height: 75rpx;
						border-radius: 50%;
					}
				}
				.userInfo{
					height: 75rpx;
					display: flex;
					flex-flow: column nowrap;
					padding-left: 30rpx;
					.userName{
						color: #D3AB58;
						font-size: 27rpx;
					}
					.userContribution{
						margin-top: 10rpx;
						color: rgb(179, 172, 172);
						font-size: 23rpx;
					}
				}
			}
			.itemRight{
				width: 30rpx;
				height: 75rpx;
				display: flex;
				align-items: center;
				justify-content: center;
				color: rgb(198,192,192);
				font-size: 23rpx;
			}
		}
	}
	.giftGiving{
		position: fixed;
		bottom: 0;
		left: 0;
		height: 200rpx;
		width: 100vw;
		background: rgb(235, 235, 235);
		.myGift{
			height: 100rpx;
			width: 100vw;
			display: flex;
			align-items: center;
			padding: 0 30rpx;
			box-sizing: border-box;
			.itemLeft{
				height: 50rpx;
				width: 50rpx;
				color: rgb(198,192,192);
				font-size: 35rpx;
				font-weight: 900;
				display: flex;
				align-items: center;
				justify-content: center;
			}
			.itemContent{
				flex-grow: 1;
				display: flex;
				align-items: center;
				padding-left: 20rpx;
				.userImage{
					height: 75rpx;
					width: 75rpx;
					image{
						height: 75rpx;
						width: 75rpx;
						border-radius: 50%;
					}
				}
				.userInfo{
					padding-left: 20rpx;
					font-size: 30rpx;
				}
			}
			.itemRight{
				width: 130rpx;
				color: #D3AB58;
				display: flex;
				align-items: center;
				image{
					height: 30rpx;
					width: 30rpx;
				}
			}
		}
	}
	.giving{
		position: fixed;
		top: 0;
		left: 0;
		height: 100vh;
		width: 100vw;
		background: rgba(0,0,0,.45);
		z-index: 2;
		display: flex;
		flex-flow: column nowrap;
		justify-content: flex-end;
		.rewardTitle{
			height: 48vh;
			width: 100vw;
			display: flex;
			flex-flow: column nowrap;
			background-color: white;
			.rewardTop{
				height: 100rpx;
				width: 100vw;
				display: flex;
				justify-content: center;
				align-items: center;
				padding-left: 70rpx;
				box-sizing: border-box;
				.text{
					flex-grow: 1;
					text-align: center;
					font-size: 30rpx;
					font-weight: 600;
				}
				image{
					height: 45rpx;
					width: 45rpx;
					padding-right: 25rpx;
				}
			}
		}
		.rewardContent{
			display: flex;
			flex-flow: row wrap;
			justify-content: space-around;
			margin: 0 40rpx;
			.rewardItem{
				height: 128rpx;
				width: 128rpx;
				display: flex;
				flex-flow: column nowrap;
				align-items: center;
				margin: 15rpx;
				.rewardImage{
					height: 96rpx;
					width: 128rpx;
					display: flex;
					justify-content: center;
					align-items: center;
					image{
						height: 75rpx;
						width: 75rpx;
						border-radius: 20rpx;
					}
				}
				.rewardPay{
					height: 32rpx;
					width: 128rpx;
					font-size: 26rpx;
					display: flex;
					justify-content: center;
					align-items: baseline;
					#changePrice{
						font-size: 17rpx;
						text-decoration: line-through;
						font-weight: 600;
					}
				}
			}
			.activeItem{
				border: 3rpx solid #D3AB58;
				.rewardPay{
					background-color: #D3AB58;
					color: whitesmoke;
				}
			}
		}
		.rewardQuantity{
			display: flex;
			justify-content: space-around;
			align-items: center;
			margin-left: 40rpx;
			margin-top: 50rpx;
			.quantityItem{
				height: 40rpx;
				width: 100rpx;
				display: flex;
				align-items: center;
				justify-content: center;
				font-size: 25rpx;
				font-weight: 600;
				border-radius: 20rpx;
				border: 2rpx solid rgb(198,192,192);
			}
			.activeQuantity{
				border: 2rpx solid #D3AB58;
				box-shadow: 0 0 10rpx 0 #D3AB58;
			}
		}
		.choose{
			display: flex;
			justify-content: space-between;
			margin: 30rpx 40rpx;
			button{
				width: 47%;
				border-radius: 50rpx;
				color: whitesmoke;
				font-size: 32rpx;
				font-weight: 600;
				span{
					font-size: 28rpx;
				}
			}
			#recharge{
				background-color: #ac9e83;
			}
			#give{
				background-color: #D3AB58;
			}
		}
	}
}
</style>