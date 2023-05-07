<template>
	<view class="container">
		<view class="Search">
			<img src="static/image/index/zsou.png" alt="">
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

.container .Search input {
	z-index: 1;
}

.container .xunlian {
	color: #334154;
	margin-top: 20rpx;
	margin-bottom: 20rpx;
}

.container .shuru {
	position: relative;
	top: -68rpx;
	left: 114rpx;
}
</style>