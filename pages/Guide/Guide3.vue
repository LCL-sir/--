<template>
	<view class="container">
		<view class="topTitle">
			请选择性别
		</view>
		<view class="main">
			<view :class="{ sexStyle1: sexStyleValue == 1 }" @click="changeNan()">
				<img src="static/image/guide/nan.png" alt="">
				<view>
					男
				</view>
			</view>
			<view :class="{ sexStyle2: sexStyleValue == 2 }" @click="changeNv()">
				<img src="static/image/guide/nv.png" alt="">
				<view>
					女
				</view>
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
			uni.navigateTo({
				url: './Guide4'
			});
		},
		// 选择男
		changeNan() {
			if (this.sexStyleValue == 1) {
				this.sexStyleValue = 0
			} else {
				this.sexStyleValue = 1;
			}
		},
		// 选择女
		changeNv() {
			if (this.sexStyleValue == 2) {
				this.sexStyleValue = 0
			} else {
				this.sexStyleValue = 2;

			}
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
	display: flex;
	position: absolute;
	justify-content: space-evenly;
	width: 100%;
	height: 380rpx;
	position: absolute;
	top: 350rpx;
}

.main>view {
	/* border: 2rpx solid #ccc; */
	width: 39%;
	border-radius: 28rpx;
	background: #FFFFFF;
	box-shadow: 20px 20px 60px #d9d9d9,
		-20px -20px 60px #ffffff;
	padding-top: 30rpx;
}

.main view view {
	margin-left: 66rpx;
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

.sexStyle1 {
	background: #5dd8d0 !important;
}

.sexStyle2 {
	background: #ECB0CD !important;
}
</style>
