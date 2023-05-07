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
			<view class="main_m">
				<view v-for="(item, index) in piqi" :key="index" @click="onrili(item)" :class="botClick == item?'bjys':''">
					{{ item }}
				</view>
			</view>
			<uni-popup ref="popup" type="bottom" class="bot">
				<view class="bao">
					<view class="xian"></view>
					<view class="t1">
						<view class="l1">晨跑</view>
						<view class="l2">6：16 &nbsp;&nbsp;&nbsp; 1556步</view>
						<view class="l3">
							<img src="../../static/image/trends/yes.png" alt="">
						</view>
					</view>
					<view class="t1">
						<view>晚间跑步</view>
						<view class="l2">18：30 &nbsp;&nbsp;&nbsp; 3554步</view>
						<view class="l3">
							<img src="../../static/image/trends/yes.png" alt="">
						</view>
					</view>
					<view class="t1">
						<view>健步</view>
						<view class="l2">12：00 &nbsp;&nbsp;&nbsp; 5000步</view>
						<view class="l4">
							<img src="../../static/image/trends/no.png" alt="">
						</view>
					</view>
					<view class="t1">
						<view>总运动量</view>
						<view class="l2">2023.05.01 &nbsp;&nbsp;&nbsp; 7000步</view>
						<view class="l4">
							<img src="../../static/image/trends/no.png" alt="">
						</view>
					</view>
				</view>
			</uni-popup>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				piqi: [30, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28,
					29, 30, 31, 1, 2, 3
				],
				botClick: 8
			}
		},
		onLoad(options) {

		},
		onShow() {

		},
		methods: {
			onrili(e) {
				console.log(e);
				this.botClick = e;
				this.$refs.popup.open('bottom')
			}
		},
	}
</script>

<style lang="scss" scoped>
	.container {
		height: 85.8vh;
		background-color: #01040D;
		border-top: 1px solid #01040D;
		color: #FFFFFF;
		padding-top: 88rpx;
	}

	.container .top {
		color: #FFFFFF;
		font-size: 44rpx;
		margin-top: 40rpx;
		margin-left: 40rpx;
	}

	.main .main_week {
		display: flex;
		justify-content: space-around;
		margin-top: 12px;
		color: #75818F;
		margin-bottom: 14px;
	}

	.main .main_m {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-around;
	}

	.main .main_m view {
		width: 14%;
		text-align: center;
		height: 30px;
	}

	.bjys {
		background-color: #5DD8D0;
		border-radius: 9px;

	}

	.xian {
		width: 200rpx;
		height: 10rpx;
		background-color: #E5E6EC;
		position: relative;
		top: 10px;
		left: 114px;
		border-radius: 6px;


	}

	.bao {
		background-color: #FFFFFF;
		border-radius: 40rpx 40rpx 0 0;
		padding-left: 40rpx;
		padding-right: 40rpx;
		border-top: 1px solid #FFFFFF;
		padding-bottom: 90rpx;
	}

	.bot {
		color: #01040D;
		
	}

	.bao .t1 {
		margin-top: 30rpx;
		height: 120rpx;
	}

	.bao .l2 {
		font-size: 13px;
		margin-top: 9px;
		margin-bottom: 9px;
		color: #9194a3;
	}

	.bao .l3 {
		position: relative;
		left: 286px;
		top: -47px;
	}
	.bao .l4 {
		position: relative;
		left: 308px;
		top: -47px;
	}
</style>