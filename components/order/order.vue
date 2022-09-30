<template>
	<view>
		<view class="type-top">
			<uni-section title="产品分类" type="line" padding>
				<uni-grid :column="3" :show-border="false" :square="false" @change="change">
					<uni-grid-item v-for="(item ,index) in type" :index="index" :key="index">
						<view class="grid-item-box">
						<!-- 	<image class="image"  mode="aspectFill" /> -->
							<text class="text">{{item.label}}</text>
						</view>
					</uni-grid-item>
				</uni-grid>
			</uni-section>
		</view>
		<view class="type-form">
			<!-- <van-cell title="客户信息" icon="location-o" :border='false'>
			</van-cell> -->
		</view>
	</view>
</template>

<script>
	export default {
		props: ['type'],
		data() {
			return {

			}
		},
		methods: {
			change(e){
				console.log(e)
			}
		},
		created() {
			console.log(this.type)
		}
	}
</script>

<style lang="scss">
	.type-top {
		background-color: #FFFFFF;
		margin-bottom: 5px;
	}
</style>
