<template>
	<view>
	<view><button type="default" @click="getdata()">发送get请求</button></view>
	<view><button type="default" @click="setdata()">存储数据到本地</button></view>
	<!-- 获取数据：uni.getStorage(),删除数据:uni.removeStorage(),用key值标识数据 -->
	<view><button type="default" @click="takephoto">拍照上传</button></view>
	<view><image v-for="item in imgList" :src="item" @click="preimage(item)"></image></view>
	<!-- #ifdef H5 -->
	<view>这段话只能在h5页面中显示</view>
	<!-- #endif -->
	<!-- #ifdef MP-WEIXIN -->
	<view>这段话只能在微信小程序中显示</view>
	<!-- #endif -->
	</view>
</template>

<script>
	export default{
		data(){
			return{
				imgList:[]
			}
		}
		,methods:{
			getdata(){
				uni.request({
					url:"http://localhost:8082/api/getlunbo",
					success(res) {
						console.log(res)
					}
				})
			},
			setdata(){
				uni.setStorage({
					key:"id",
					data:80,
					success() {
						console.log("存储成功")
					}
					})
			},
			takephoto(){
				uni.chooseImage({
					count:5,
					success:res=> {
						
						this.imgList=res.tempFilePaths;
					
					}
				})
			},
			preimage(current){
				console.log(current)
				uni.previewImage({
					current,
					urls:this.imgList,
					loop:true,
					indicator:"default"
				})
			}
		}
	}
</script>

<style>
</style>
