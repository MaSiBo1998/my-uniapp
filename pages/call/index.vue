<template>
	<view >
		客服链接
		<map></map>
		<van-button @click="toHome">首页</van-button>
	</view>
</template>

<script>
	export default {
		onLoad: function(option){
			console.log(option)
			const eventChannel = this.getOpenerEventChannel();
			eventChannel.emit('dating',{data:'触发主页面事件,并向主页面传递的数据'})
			eventChannel.on('dating',function(data){
				console.log(data,'获取主页面传递的数据')
			})
		},
		data(){
			return {
				
			}
		},
		methods: {
			toHome() {
				uni.switchTab({
					url:'/pages/index/index',
					success(res){
						console.log(res)
					},
					fail(err){
						console.log(err)
					}
				})
			}
		}
	}
</script>

<style>
</style>