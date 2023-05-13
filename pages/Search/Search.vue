<template>
	<view class="container">
		<view class="Search">
			<view class="kuang">
				<img src="static/image/index/zsou.png" @click="imgClick('fade')">
			</view>
			<div class="shuru">
				<input type="text" placeholder="搜索课程" />
			</div>
			<view class="xunlian">
				推荐
			</view>
			<view>
				<img src="static/image/index/datu.png" @click="toVideo()">
			</view>
		</view>
		<uni-transition ref="ani" custom-class="transition" :mode-class="modeClass" :styles="styles" :show="show"
			class="donghua">
			<img src="static/image/login/loding.gif" alt="">
		</uni-transition>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				dianStyle: 'flase',
				show: false,
				modeClass: 'fade',
				styles: {},
				showLoading: true
			}
		},
		onLoad(options) {

		},
		onShow() {

		},
		methods: {
			imgClick(type) {
				console.log(123)
				this.show = !this.show
				this.modeClass = type
				setTimeout(() => {
					this.show = !this.show
					uni.navigateTo({
						url: '../videoPage/videoPage'
					});
				}, 1000)
			},
			toVideo(){
				uni.navigateTo({
					url: '../videoPage/videoPage?id='+'../../static/video/video2.mp4'
				});
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

	.donghua {
		position: relative;
		width: 51vw;
		height: 27vh;
		top: -535px;
		left: 65px;
		background-color: rgba(255, 255, 255, 0.72);
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 29px;

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