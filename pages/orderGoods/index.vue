<template>
	<order :type="type"></order>
</template>

<script>
	export default {
		onLoad(option){
			let _this = this
			const eventChannel = this.getOpenerEventChannel();
			// eventChannel.emit('dating',{data:'触发主页面事件,并向主页面传递的数据'})
			eventChannel.on('putOrderType',function(data){
				console.log(data)
				_this.type = data
			})
		},
		data(){
			return {
				type:[]
			}
		},
		methods: {
			
		},
		created(){
			
		}
	}
</script>

<style>
</style>