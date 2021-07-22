<template>
	<view>
	<view>hello</view>
	<navigator url="/pages/detail/detail?id=80" open-type="navigate">跳转至详情页</navigator>
	<navigator url="/pages/message/message" open-type="switchTab">跳转至信息页</navigator>
	<!-- 另外还有uni.navigeteTo(object)方法跳转至页面，uni.switchTab(object)跳转至tabbar页面,uni.redirectTo(object)跳转至页面并销毁原来的页面，无返回键的意思 -->
	</view>
</template>

<script>
	export default{
		
	}
</script>

<style>
</style>
