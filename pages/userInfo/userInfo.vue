<template>
	<view class="container">
		<view class="top">登录/注册</view>
		<view class="sk">
			<view>
				<input type="text" placeholder="请输入账号" />
			</view>
			<view>
				<input type="text" placeholder="请输入密码" />
			</view>
			<view @click="tomy()">
				登录
			</view>
		</view>
		<view class="duo">
			<img src="../../static/image/login/duo.png" alt="">
		</view>
		<view class="yue">
			<view @click="dian" :class="dianStyle ? '' : 'dian'"></view>
			<view>我已阅读并同意易动用户协议和隐私政策</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			dianStyle: 'flase'
		}
	},
	methods: {
		dian() {
			this.dianStyle = !this.dianStyle;
		},
		tomy() {
			uni.switchTab({
				url: '../my/my'
			});
		}
	}
}
</script>

<style scoped>
.container {
	background-color: #1E0D48;
	width: 100vw;
	height: 90.2vh;
	padding: 40rpx 40rpx 0 40rpx;
}

.container .top {
	color: #fff;
	font-size: 40rpx;
	margin-left: 20rpx;
}

.container .sk>view {
	width: 80%;
	height: 92rpx;
	background-color: rgba(255, 255, 255, 0.2);
	margin-top: 60rpx;
	border-radius: 50rpx;
	margin-left: 36rpx;
	display: flex;
	justify-content: space-evenly;
	align-items: center;
	color: #fff;
}

.container .sk>view:nth-child(3) {
	background-color: #6C5DD3;
}

.container .duo {
	position: relative;
	top: 480rpx;
	left: 146rpx;
}

.container .yue {
	position: relative;
	top: 520rpx;
	left: 34rpx;
	color: #fff;
	display: flex;
	align-items: center;
}

.container .yue view:nth-child(1) {
	width: 14rpx;
	height: 14rpx;
	border-radius: 50%;
	border: 1rpx solid #ccc;
}

.container .yue view:nth-child(2) {
	margin-left: 16rpx;
}

.dian {
	background-color: rgb(6, 201, 39);
	border: 0;
}
</style>
