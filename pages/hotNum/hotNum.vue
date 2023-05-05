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
				title: "饮食摄入",
				numberInfo: "0千卡"
			},
			{
				title: "运动消耗",
				numberInfo: "0千卡"
			}, {
				title: "碳水",
				numberInfo: "0/237克"
			}, {
				title: "蛋白质",
				numberInfo: "0/94克"
			}, {
				title: "脂肪",
				numberInfo: "0/63克"
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
