<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<!-- 父组件传给子组件 -->
		<view>
			<test :title="title" @myEven="getNum"></test>
		</view>
		这是子组件传给父组件的数据{{num}}
		<testa :name1="name1"></testa>
		<testb @c="getName"></testb>
		这是testb子组件给index父组件传递的数据:{{name}}
		<view class="page">
			<text class="example-info">可以同时选择日期和时间的选择器</text>
			<uni-section :title="'日期用法：' + single" type="line"></uni-section>
			<view class="example-body">
				<uni-datetime-picker type="date" :value="single" start="2021-3-20" end="2021-6-20" @change="change" />
			</view>
			
		</view>
	</view>
</template>

<script>
	import test from '../../components/test.vue'
	import testa from '../../components/testa.vue'
	import testb from '../../components/testb.vue'
	export default {
		data() {
			return {
				title: 'Hello',
				num: 0,
				name1: '欧力',
				name: '大脑',
				single: '2021-04-3',
				datetimesingle: '2021-04-3',
				range: ['2021-03-8', '2021-4-20'],
				datetimerange: ['2021-03-20 20:10:10', '2021-05-10 10:10:10'],

			}
		},
		watch: {
			datetimesingle(newval) {
				console.log('单选:', this.datetimesingle);
			},
			range(newval) {
				console.log('范围选:', this.range);
			},
			datetimerange(newval) {
				console.log('范围选:', this.datetimerange);
			}
		},
		mounted() {
			setTimeout(() => {
				this.datetimesingle = '2021-5-1'
				this.single = '2021-5-1'
			}, 1000)
		},

		methods: {
			getNum(num) {
				console.log(num);
				this.num = num
			},
			getName(name) {
				this.name = name
			},
			change(e) {
				this.single = e
				console.log('-change事件:', e);
			}
		},
		components: {
			test: test,
			testa: testa,
			testb: testb
		}
	}
</script>

<style lang="scss">

	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
