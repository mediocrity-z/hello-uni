<template>
	<view>
		
		<view>这是b组件的数据:{{num}}</view>
		<button type="default" @click="sendName">testb给父组件传递数据</button>
	</view>
</template>

<script>
	export default {
		name:"testb",
		data() {
			return {
				name:'何超',
				num:0
			};
		},
		methods:{
			sendName(){
				this.$emit('c',this.name)
			},
			
		},
		created() {
			uni.$on('updateNum',num=>{
				this.num+=num;
			
			})
		}
	}
</script>

<style>
button{
	background-color: #F0AD4E;
}
</style>
