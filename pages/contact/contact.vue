<template>
	<view>
	<view><h1>这是我们</h1></view>
	<view class="box" v-for="(item,id) in list" :key="id">{{item.name}}</view>
	<view><button type="default" @click="refresh">下拉刷新</button></view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				list:[{name:'搞基超',id:1},{name:'欧乐超',id:2},{name:'欧了超',id:3},{name:'搞基超',id:4},{name:'欧乐超',id:5},{name:'欧了超',id:6},{name:'搞基超',id:7},{name:'欧乐超',id:8},{name:'欧了超',id:9}]
			}
		},
		methods:{
			refresh(){
				uni.startPullDownRefresh({
					
				})
			}
		},
		onPullDownRefresh() {
			console.log("触发了下拉刷新")
			setTimeout(()=>{
				this.list=[{name:'欧乐超',id:2},{name:'欧了超',id:3},{name:'搞基超',id:1}]
			
			uni.stopPullDownRefresh()
			},2000)
		},
		onReachBottom() {
			console.log("页面触底");
			this.list=[...this.list,...[{name:'欧乐超',id:2},{name:'欧了超',id:3},{name:'欧乐瑶',id:1}]]
		}
	}
</script>

<style lang="less">
	.box{
		line-height: 100px;
	}
</style>
