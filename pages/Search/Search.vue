<template>
	<view class="container">
		<view class="Search">
			<view class="kuang">
				<img src="static/image/index/zsou.png" @click="imgClick()">
			</view>
			<div class="shuru">
				<input type="text" placeholder="搜索课程" />
			</div>
			<view class="xunlian">
				推荐
			</view>
			<view>
				<img src="static/image/index/datu.png" alt="">
			</view>
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
			imgClick() {
				console.log(123)
			}
		},
	}
</script>

<style lang="scss" scoped>
	.container {
		padding: 0 40rpx;
	}

	.container .Search {
		margin-top: 40rpx;
	}

	.container .Search .kuang {
		background-color: #f2f4f5;
		height: 42px;
		border-radius: 24px;
	}

	.container .Search .kuang img {
		width: 40rpx;
		height: 40rpx;
		position: relative;
		top: 24rpx;
		left: 580rpx;
	}

	.container .Search input {
		z-index: 1;
		width: 500rpx;
	}

	.container .xunlian {
		color: #334154;
		margin-top: 20rpx;
		margin-bottom: 20rpx;
	}

	.container .shuru {
		position: relative;
		top: -68rpx;
		left: 52rpx;
		width: 500rpx;
	}
</style>