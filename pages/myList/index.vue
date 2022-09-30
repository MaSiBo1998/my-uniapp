<template>
	<view >
		我的订单
		<van-button type="warning" @click="toUserPage">个人中心</van-button>
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
				uni.switchTab({
					url: '/pages/user/index'
				})
			}
		},
	}
</script>

<style>
</style>