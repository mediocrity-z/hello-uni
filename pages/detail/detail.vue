<template>
	<view>
		<view><text>唱歌打篮球rap</text></view>
		<view><text class="ouligei" selectable space="emsp"><text>蔡徐坤</text>唱歌 打篮球 rap</text></view>
		<view>{{msg}}</view>
		<view><image :src="imgurl"></image></view>
		<view v-for="(item,id) in list" :key="id">名字:{{item.name}} 序号:{{item.id}}</view>
		<!-- 事件对象：$event -->
	</view>
</template>

<script>
	export default{
		onLoad(options) {
			console.log(options)
		}
		,data(){
			return {
				msg:'虎牙搜何超',
				imgurl:"../../static/logo.png",
				list:[{
					name:'何超',
					id:1
				},
				{
					name:'欧力',
					id:2,
					}]
			}
		}
	}
</script>

<style lang="scss">
	.ouligei{
		color: $uni-bg-color-mask;
		text{
			color: blue;
		}
	}
</style>
