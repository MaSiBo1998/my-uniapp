<template>
	<view >
		接单大厅
		<van-button type="warning" @click="toUserPage">客服链接</van-button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			toUserPage() {
				uni.navigateTo({
					url: '/pages/call/index?id=14&name=masibo',
					events:{
						dating: function(data){
							console.log('主页面的事件',data)
						}
					},
					success(res) {
						res.eventChannel.emit('dating',{data:'跳转成功发送,大厅传递的数据'})
					}
				})
				
			}
		},
	}
</script>

<style>
</style>