<template>
	<view class="main">
		<view>{{ numberValue }}</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			numberValue: 4
		}
	},
	onLoad() {
		this.timeOut();
	},
	methods: {
		timeOut() {
			this.numberValue -= 1;
			if (this.numberValue === 0) {
				uni.navigateTo({
					url: '../trueRun/trueRun'
				});
			}
			else {
				setTimeout(this.timeOut, 1000);
			}
		}
	}
}
</script>

<style>
.main {
	width: 100vw;
	height: 100vh;
	background-color: #6C5DD3;
}

.main view {
	font-size: 30px;
	color: #ffffff;
	position: absolute;
	left: 292rpx;
	top: 454rpx;
	font-size: 254rpx;
}
</style>
