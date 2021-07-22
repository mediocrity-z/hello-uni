<template>
	<view>
	<view>
		这是父组件传递给子组件的数据{{title}}
	</view>
	<button @click="sendNum">给父组件传递数据</button>
	</view>
</template>

<script>
	export default {
		name:"test",
		data() {
			return {
				num:3
			}
		},
	props:['title'],
	  created() {
	  	console.log('created')
	  },
	  mounted() {
	  	console.log('mounted')
	  },
	  methods:{
		  sendNum(){
			console.log('向父组件传值')
			this.$emit('myEven',this.num)
		  }
	  }
	}
</script>

<style lang="less">
button{
	background-color: #007AFF;
}
</style>
