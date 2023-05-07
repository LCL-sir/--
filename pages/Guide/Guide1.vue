<template>
	<view class="container">
		<view class="mian">
			<img src="static/image/guide/guide2.png">
		</view>
		<view class="textTitle">
			针对跑者的专业软件
		</view>
		<view class="point">
			<view></view>
			<view></view>
			<view></view>
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
				url: './Guide2'
			});
		}
	},
}
</script>

<style scoped>
.container {
	position: relative;
	width: 100vw;
	height: 70vh;
	background-image: url(../../static/image/beijing.png);
	background-repeat: no-repeat;
	background-size: 100% 92%;
	background-position: 0 100rpx;
	;
}
.mian {
	margin: auto;
	position: absolute;
	top: 20vh;
	right: 25vw;
}
.textTitle {
	position: absolute;
	bottom: -40rpx;
	left: 25%;
	font-size: 48rpx;
}
.point {
	width: 200rpx;
	height: 20rpx;
	position: absolute;
	bottom: -100rpx;
	left: 39%;
	display: flex;
	justify-content: space-evenly;
	align-items: center;
}
.point view {
	border-radius: 50%;
	width: 16rpx;
	height: 16rpx;
	background-color: #b4aafc;
}
.point view:nth-child(2) {
	background-color: #6C5DD3;

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
}</style>
