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
	height: 85.8vh;
	background-color: #01040D;
	border-top: 1px solid #01040D;
}

.container .top {
	color: #FFFFFF;
	font-size: 44rpx;
	margin-top: 40rpx;
	margin-left: 40rpx;
}
</style>
