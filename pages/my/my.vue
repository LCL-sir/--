<template>
	<view class="container">
		<view>
			<img src="../../static/image/my/userBook.png" alt="">
			<span>Dear 璐</span>
			<span>易跑ID：123456789</span>
		</view>
		<view class="myData">
			<view></view>
			<view>我的数据</view>
		</view>
		<view class="myDataNumber">
			<view>
				<img src="../../static/image/my/run.png" alt="">
				<span>35</span>
				<view>运动记录/分钟</view>
			</view>
			<view>
				<img src="../../static/image/my/node.png" alt="">
				<span>17</span>
				<view style="margin-top: 5px;">体重记录/天</view>
			</view>
			<view>
				<img src="../../static/image/my/hot.png" alt="">
				<span>6</span>
				<view>热量记录/天</view>
			</view>
		</view>
		<view class="zhoubian">
			<view>
				<view class="zhoubianList">
					<img src="../../static/image/my/xunzhang.png" alt="">
					<span>勋章墙</span>
				</view>
				<view>
					更多 >
				</view>
			</view>
			<view>
				<view class="zhoubianList">
					<img src="../../static/image/my/jiangbei.png" alt="">
					<span>赛事</span>
				</view>
				<view>
					更多 >
				</view>
			</view>
			<view>
				<view class="zhoubianList">
					<img src="../../static/image/my/qizi.png" alt="">
					<span>活动</span>
				</view>
				<view>
					更多 >
				</view>
			</view>
		</view>
		<view class="userInfo">
			<view>
				<view>个人信息</view>
				<view>></view>
			</view>
			<view>
				<view>通用设置</view>
				<view>></view>
			</view>
			<view>
				<view>隐私设置</view>
				<view>></view>
			</view>
			<view>
				<view>用户协议</view>
				<view>></view>
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
	margin: 20rpx 40rpx;
}

.container>view:nth-child(1) span:nth-child(2) {
	position: relative;
	top: -52rpx;
	left: 28rpx;
	font-size: 40rpx;
}

.container>view:nth-child(1) span:nth-child(3) {
	position: relative;
	left: -104rpx;
	color: #75818F;
	font-size: 28rpx;
}

.container .myData {
	margin-top: 28rpx;
	display: flex;
	font-size: 40rpx;
	line-height: 38rpx;
}

.container .myData view:nth-child(1) {
	width: 10rpx;
	height: 40rpx;
	background-color: #9586FB;
	margin-right: 10rpx;

}

.container .myDataNumber {
	display: flex;
	justify-content: space-around;
}

.container .myDataNumber>view {
	margin-top: 40rpx;
	background-color: #9586FB;
	width: 200rpx;
	height: 220rpx;
	border-radius: 40rpx;
}

.container .myDataNumber>view img {
	margin-top: 40rpx;
	margin-left: 40rpx;
}

.container .myDataNumber>view span {
	font-size: 40rpx;
	position: relative;
	top: 45rpx;
	left: -30rpx;
}

.container .myDataNumber>view view {
	font-size: 24rpx;
	position: relative;
	top: 45rpx;
	left: 14rpx;
}

.container .zhoubian {
	margin-top: 40rpx;
}

.container .zhoubian>view {
	background-color: #E8EAEC;
	margin-top: 20rpx;
	border-radius: 24rpx;
	height: 72rpx;
	display: flex;
	justify-content: space-between;
	padding: 0 22rpx;
	align-items: center;
}

.zhoubian .zhoubianList {
	display: flex;
	align-items: center;
}

.zhoubian .zhoubianList img {
	margin-right: 10rpx;
}
.userInfo {
	margin-top: 40rpx;
}
.userInfo>view {
	border-bottom: 1px solid #ccc;
	display: flex;
	justify-content: space-between;
	padding: 0 24rpx;
	height: 76rpx;
	align-items: center;
}
</style>
