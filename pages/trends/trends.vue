<template>
	<view class="container">
		<view class="top">5月2023</view>
		<view class="main">
			<view class="main_week">
				<span>S</span>
				<span>M</span>
				<span>T</span>
				<span>W</span>
				<span>T</span>
				<span>F</span>
				<span>S</span>
			</view>
			<view class="main_m">
				<view v-for="(item, index) in piqi" :key="index" @click="onrili(item)">{{ item }}</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			piqi: [30, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 1, 2, 3]
		}
	},
	onLoad(options) {

	},
	onShow() {

	},
	methods: {
		onrili(e){
			console.log(e);
		}
	},
}
</script>

<style lang="scss" scoped>
.container {
	height: 85.8vh;
	background-color: #01040D;
	border-top: 1px solid #01040D;
	color: #FFFFFF;
}

.container .top {
	color: #FFFFFF;
	font-size: 44rpx;
	margin-top: 40rpx;
	margin-left: 40rpx;
}

.main .main_week {
	display: flex;
	justify-content: space-around;
	margin-top: 12px;
	color: #75818F;
  margin-bottom: 14px;
}

.main .main_m {
	display: flex;
	flex-wrap: wrap;
	justify-content: space-around;
}

.main .main_m view {
	width: 14%;
	text-align: center;
	height: 30px;
}
</style>
