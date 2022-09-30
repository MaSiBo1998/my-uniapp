<template>
	<view class="container">
		<uni-grid :column="2" :highlight="true" @change="change">
			<uni-grid-item v-for="(item, index) in serviceList" :index="index" :key="index">
				<view class="grid-item-box" style="background-color: #fff;">
					<uni-icons type="image" :size="30" color="#777" />
					<text class="text">{{item.label}}</text>
				</view>
			</uni-grid-item>
		</uni-grid>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				serviceList: [{
					label: '门锁'
				}, {
					label: '晾衣架'
				}]
			}
		},
		methods: {
			change(e) {
				if (e.detail.index == 0) {
					this.toOrder([{label:'安装',url:'static/c1.png'}, {label:'维修',url:'static/c2.png'}]) // 门锁
				} else {
					this.toOrder([{label:'安装',url:'static/c3.png'}, {label:'维修',url:'static/c4.png'}]) // 晾衣架
				}
			},
			toOrder(type) {
				uni.navigateTo({
					url: '/pages/orderGoods/index',
					events: {
						putOrderType: function(type) {
							return type
						}
					},
					success(res) {
						res.eventChannel.emit('putOrderType', type)
					}
				})
			}
		}
	}
</script>

<style>
	.container {
		padding: 20px;
		font-size: 14px;
		line-height: 24px;
	}
</style>
