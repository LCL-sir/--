<template>
	<view>
		<div class="top">
			<img src="../../static/image/index/index1.png" alt="">
		</div>
		<div class="main">
			<view class="main_1">
				<view>
					<view class="main_1_si_paobu"><img src="../../static/image/index/paobu.png" alt=""></view>
					<text>跑步</text>
				</view>
				<view>1</view>
				<view>1</view>
				<view>1</view>
			</view>
			<view>1</view>
			<view>1</view>
		</div>
		<div class="bottom"></div>
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
	.main_1 {
		width: 95vw;
		border: 1px solid #707070;
		height: 200rpx;
		margin: 10rpx auto;
		border-radius: 40rpx;
		display: flex;
		justify-content: space-around;
		align-items: center
	}

	.main_1_si {
		/* display: flex; */
	}

	.main_1_si_paobu {
		background-color: #11CEBA;
		width: 100rpx;
		height: 100rpx;
		border-radius: 50%;
		text-align: center;
		
	}
	.main_1_si_paobu img {
			margin-top: 24rpx;
		}
</style>
