<template>
	<view class="container">
		<view class="topTitle">
			请选择身高
		</view>
		<view class="main">
			<view class="mian_black">
				cm
			</view>
			<view class="shu">
				<input type="number" focus confirm-type="next">
			</view>
		</view>
		<view class="bottom" @click="toPass">
			完成
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			sexStyleValue: 0
		}
	},
	onLoad(options) {

	},
	onShow() {

	},
	methods: {
		// 跳转到下一页
		toPass() {
			// 缓存到本地，下次跳过引导页
			uni.setStorageSync('GuideValue', '1');
			uni.navigateTo({
				url: '../userInfo/userInfo'
			});
			// uni.switchTab({
			// 	url: '/pages/runbu/runbu'
			// });
		}
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

.shu {
	border-bottom: 1px solid #ccc;
	width: 122rpx;
	position: relative;
	top: 120rpx;
	padding-left: 80rpx;
}
</style>
