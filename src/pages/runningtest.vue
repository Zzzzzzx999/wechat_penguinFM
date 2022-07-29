<template>
	<div class="runningTest">
        <button @click="test2">点击测试</button>
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
        showHelp(help) {
            console.log('输出',help);
        },
		test(){
			/* const user1={id:7,name:'周'}
			const user2={id:10,age:22}
			const all_user={...user1,...user2}
			console.log(all_user); */
            var helpText = [
                {'id': 'email', 'help': 'Your e-mail address'},
                {'id': 'name', 'help': 'Your full name'},
                {'id': 'age', 'help': 'Your age (you must be over 16)'}
            ]
            for (var i = 0; i < helpText.length; i++) {
                var item = helpText[i];
                setTimeout(() => {
                    this.showHelp(item.help);
                }, 0);
                console.log('@',item.help);
                this.test2(item.id)
            }
		},
        test2(){
            var arr_text = [
                {'id': '1', 'name': 'zhou'},
                {'id': '2', 'name': 'huang'},
                {'id': '3', 'name': 'lou)'}
            ]
            setTimeout(() => {
                arr_text[2].name = 'zhang'
                console.log('arr_text=',arr_text);
            }, 0);
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