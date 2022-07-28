<template>
	<div class="runningTest">
		 <button @click="test">点击测试</button>
	</div>
</template>

<script>
export default {
	name:'runningTest',
	data() {
		return {
			 
		};
	},
	methods: {
		test(){
			/* const user1={id:7,name:'周'}
			const user2={id:10,age:22}
			const all_user={...user1,...user2}
			console.log(all_user); */
		}
	}
	
}
</script>

<style lang="less">
.runningTest{
	height: 60vh;
	display: flex;
	justify-content: center;
	align-items: center;
	button{
		border-radius: 20rpx;
		background-color: antiquewhite;
	}
}
</style>