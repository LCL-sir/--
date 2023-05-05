<template>
	<view class="container">
		<view class="Search">
			<img src="../../static/image/index/Search.png" alt="">
			<input type="text" />
			<view class="xunlian">
				推荐
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
	}
</style>