<template>
	<view class="container">
		<view v-for="(item, index) in tizhong" :key="index" class="tiList">
			<view>{{ item.title }}</view>
			<view>{{ item.numberInfo }}</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			tizhong: [{
				title: "体重",
				numberInfo: "0.00公斤"
			},
			{
				title: "体脂率",
				numberInfo: "--%"
			}, {
				title: "身高",
				numberInfo: "0.00厘米"
			}, {
				title: "实时心率",
				numberInfo: "--次/分钟"
			}, {
				title: "睡眠",
				numberInfo: "--次/分钟"
			}]
		}
	},
	methods: {

	}
}
</script>

<style scoped>
.container {
	padding: 0 40rpx;
}

.tiList {
	margin-top: 28rpx;
	background-color: #E8EAEC;
	height: 190rpx;
	border-radius: 36rpx;
	padding: 30rpx 0 0 52rpx;
	box-sizing: border-box;
}

.tiList>view:nth-child(1) {
	color: #9586FB;
	font-size: 42rpx;
}

.tiList>view:nth-child(2) {
	font-size: 39rpx;
	margin-top: 20rpx
}
</style>
