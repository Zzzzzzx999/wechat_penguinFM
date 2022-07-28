<template>
	<div class="channelSorting">
		<div class="functionalArea">
			<div class="functionalItem">
				<div class="itemLeft">
					<image src="../static/icon/channelSorting/书城.png"></image>
					<span>书城</span>
				</div>
				<div class="itemRight">
					<image src="../static/icon/channelSorting/菜单-展开.png"></image>
				</div>
			</div>
			<div class="functionalItem">
				<div class="itemLeft">
					<image src="../static/icon/channelSorting/帽子,知识,智慧,学识jurassic.png"></image>
					<span>知识</span>
				</div>
				<div class="itemRight">
					<image src="../static/icon/channelSorting/菜单-展开.png"></image>
				</div>
			</div>
			<div class="functionalItem">
				<div class="itemLeft">
					<image src="../static/icon/channelSorting/爱心块状.png"></image>
					<span>情感</span>
				</div>
				<div class="itemRight">
					<image src="../static/icon/channelSorting/菜单-展开.png"></image>
				</div>
			</div>
			<div class="functionalItem">
				<div class="itemLeft">
					<image src="../static/icon/channelSorting/木马.png"></image>
					<span>亲子</span>
				</div>
				<div class="itemRight">
					<image src="../static/icon/channelSorting/菜单-展开.png"></image>
				</div>
			</div>
			<div class="functionalItem">
				<div class="itemLeft">
					<image src="../static/icon/channelSorting/音乐.png"></image>
					<span>音乐</span>
				</div>
				<div class="itemRight">
					<image src="../static/icon/channelSorting/菜单-展开.png"></image>
				</div>
			</div>
			<div class="functionalItem">
				<div class="itemLeft">
					<image src="../static/icon/channelSorting/民间.png"></image>
					<span>相声</span>
				</div>
				<div class="itemRight">
					<image src="../static/icon/channelSorting/菜单-展开.png"></image>
				</div>
			</div>
			<div class="functionalItem">
				<div class="itemLeft">
					<image src="../static/icon/channelSorting/头条-1.png"></image>
					<span>头条</span>
				</div>
				<div class="itemRight">
					<image src="../static/icon/channelSorting/菜单-展开.png"></image>
				</div>
			</div>
			<div class="functionalItem">
				<div class="itemLeft">
					<image src="../static/icon/channelSorting/娱乐.png"></image>
					<span>娱乐</span>
				</div>
				<div class="itemRight">
					<image src="../static/icon/channelSorting/菜单-展开.png"></image>
				</div>
			</div>
		</div>
        <player></player>
	</div>
</template>

<script>
import player from "../pages/player/player";
export default {
	name:"channelSorting",
    components:{player},
	data() {
		return {
			
		}
	},
}
</script>

<style lang="less">
.functionalArea{
    display: flex;
    flex-flow: column nowrap;
    margin-top: 20rpx;
    .functionalItem{
		height: 88rpx;
		width: 100%;
		padding: 0 40rpx;
		box-sizing: border-box;
		display: flex;
		justify-content: space-between;
		align-items: center;
		.itemLeft{
			width: 50%;
			display: flex;
			align-items: center;
			image{
				width: 35rpx;
				height: 35rpx;
			}
			span{
				font-size: 30rpx;
				font-weight: 500;
				padding-left: 20rpx;
			}
		}
		.itemRight{
			width: 50%;
			display: flex;
			justify-content: flex-end;
			align-items: center;
			color: darkgrey;
			font-size: 29rpx;
			image{
				width: 25rpx;
				height: 25rpx;
				margin-left: 20rpx;
			}
		}
    }
}
.wx-slider-thumb {
    display: none;
}
</style>