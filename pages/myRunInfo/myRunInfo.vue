<template>
	<view class="container">
		<view class="top">
			<img src="../../static/image/my/userBook.png" alt="">
		</view>
		<view class="main">
			<view>运动距离:0.00Km</view>
			<view>
				<view>
					<view>0T</view>
					<view>累计运动时常</view>
				</view>
				<view>
					<view>0.00Km</view>
					<view>最大里程(Km)</view>
				</view>
			</view>
		</view>
		<view>
			<img src="../../static/image/my/myRun.png" alt="">
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {

		}
	},
	methods: {

	}
}
</script>

<style>
.container {
	padding: 0 40rpx;
}

.container .top {
	position: relative;
	top: 60rpx;
	left: 10rpx;
}

.container .main {
	background-color: #9586FB;
	height: 360rpx;
	width: 87%;
	margin: 0 auto;
	border-radius: 28rpx;
	color: #fff;
}

.container .main>view:nth-child(1) {
	position: relative;
	top: 66rpx;
	left: 142rpx;
	font-size: 38rpx;
}

.container .main>view:nth-child(2) {
	display: flex;
	justify-content: space-evenly;
	margin-top: 142rpx;
	font-size: 38rpx;
	text-align: center;
}
</style>
