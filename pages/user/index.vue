<template>
	<view >
		个人中心
		<van-button @click="getName">点击获取用户姓名</van-button>
		<text>姓名:{{name}}</text>
		<van-uploader />
	</view>
</template>

<script>
	export default {
		data(){
			return {
				name:''
			}
		},
		methods: {
			getName(){
				let _this = this
				uni.getStorage({
					key: 'name',
					success(res){
						_this.name = res.data
					}
				})
			}
		},
		onLoad() {
			uni.setStorage({
				key:'name',
				data:'masibo',
				success: function(){
					console.log('用户姓名存储成功')
				}
			})
		}
	}
</script>

<style>
</style>