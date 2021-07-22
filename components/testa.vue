<template>
	<view>
		这是index父组件给testa子组件传的值:{{name1}}
	
	<!-- 兄弟组件间的通信 -->
	<view><button type="default" @click="addNum">a组件修改b组件的数据</button></view>
	</view>
</template>

<script>
	export default {
		name:"testa",
		data() {
			return {
				
			};
		},
		props:['name1'],
		methods:{
			addNum(){
				uni.$emit('updateNum',10)
			}
		}
	}
</script>

<style>

</style>
