<template>
	<view class="container">
		<view>
			<view class="title1">累计跑量 > </view>
			<span class="title2">0.00</span>
			<span class="title3">Km</span>
		</view>
		<view class="week">
			<view class="title1" style="margin-top:20px">本周跑量 > </view>
			<img src="../../static/image/index/zhousun.png" alt="">
		</view>
		<view class="liSi">
			<view>
				<img src="../../static/image/index/yundong.png" alt="">
				<span>活动</span>
			</view>
			<view>
				<img src="../../static/image/index/hot.png" alt="">
				<span>动态</span>
			</view>
			<view>
				<img src="../../static/image/index/jiaoxue.png" alt="">
				<span>教程</span>
			</view>
			<view>
				<img src="../../static/image/index/xunzhang.png" alt="">
				<span>勋章</span>
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
	onLoad() {
		// 只要页面显示 就往本地存储变量，保证用户不在打开引导页
		try {
			uni.setStorageSync('GuideValue', '1');
		} catch (e) {
			console.log(e)
		}
	},
	methods: {

	}
}
</script>

<style>
.container {
	background-color: #6C5DD3;
	width: 100vw;
	height: 85.8vh;
}

.container .title1 {
	position: relative;
	top: 88rpx;
	left: 80rpx;
	color: #ffffff;
	font-size: 40rpx;
}

.container .title2 {
	position: relative;
	color: #fff;
	font-size: 35px;
	top: 53px;
	left: 60px;
}

.container .title3 {
	position: relative;
	top: 54px;
	left: 67px;
	color: #fff;
}

.container .week img {
	position: relative;
	top: 65px;
	left: 65px;
}

.container .liSi {
	display: flex;
	position: relative;
	top: 91px;
	margin: 0 20px;
	height: 200px;
	justify-content: space-around;
	align-items: center;
	flex-wrap: wrap;
}

.container .liSi view {
	width: 45%;
	height: 150rpx;
	border-radius: 16rpx;
	background: url(../../static/image/index/bj.png) no-repeat;
}
.container .liSi>view img{
	margin: 10px;
}
.container .liSi>view span{
	position: relative;
    top: -21px;
    font-size: 20px;
    font-weight: 600;
}
</style>
