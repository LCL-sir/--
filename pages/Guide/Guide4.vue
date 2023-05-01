<template>
	<view class="container">
		<view class="topTitle">
			请选择体重
		</view>
		<view class="main">
			<view class="mian_black">
				kg
			</view>

		</view>
		<view class="bottom" @click="toPass">
			下一步
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {

		}
	},
	onLoad(options) {

	},
	onShow() {

	},
	methods: {
		// 跳转到下一页
		toPass() {
			uni.navigateTo({
				url: './Guide5'
			});
		},

	},
}
</script>

<style scoped>
.container {
	position: relative;
}

.topTitle {
	position: absolute;
	top: 70rpx;
	left: 70rpx;
	font-size: 40rpx;
	color: #707070;
}

.main {
	position: absolute;
	top: 340rpx;
	width: 100vw;
	margin-left: 36%;
}

.main .mian_black {
	width: 200rpx;
	height: 100rpx;
	background-color: #01040D;
	border-radius: 24rpx;
	color: #FFFFFF;
	text-align: center;
	line-height: 100rpx;
}

.bottom {
	width: 400rpx;
	height: 70rpx;
	background-color: #6C5DD3;
	border-radius: 18px;
	text-align: center;
	line-height: 70rpx;
	color: #ffffff;
	position: absolute;
	top: 81vh;
	left: 27vw;
}
</style>
