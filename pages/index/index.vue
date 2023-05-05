<template>
	<view class="container">
		<view class="top">
			<view>
				<img src="../../static/image/index/readme.png" alt="">
			</view>
			<view>
				<img src="../../static/image/index/xinxi.png" alt="">
			</view>
			<view>
				<img src="../../static/image/index/ling.png" alt="">
			</view>
		</view>
		<view class="Search" @click="toSearch()">
			<img src="../../static/image/index/Search.png" alt="">
		</view>
		<view class="sheng">
			<img src="../../static/image/index/sheng.png" alt="">
		</view>
		<view class="xunlian">
			训练
		</view>
		<view class="xunList">
			<view>
				<img src="../../static/image/index/01.png" alt="">
			</view>
			<view>
				<img src="../../static/image/index/02.png" alt="">
			</view>
			<view>
				<img src="../../static/image/index/04.png" alt="">
			</view>
			<view>
				<img src="../../static/image/index/05.png" alt="">
			</view>
		</view>
		<view class="xunlian">
			活动
		</view>
		<view>

			<uni-swiper-dot :info="info" :current="current" field="content" :mode="mode">
				<swiper class="swiper-box" @change="change" @click="toPass()">
					<swiper-item v-for="(item, index) in info" :key="index">
						<view class="swiper-item">
							<!-- {{ item.content }} -->
							<img :src="item.content" alt="">

						</view>
					</swiper-item>
				</swiper>
			</uni-swiper-dot>

		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			info: [{
				content: '../../static/image/index/l1.png'
			}, {
				content: '../../static/image/index/l2.png'
			}, {
				content: '../../static/image/index/l3.png'
			}],
			current: 0,
			mode: 'round',
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
		// 跳转到下一页
		toPass() {
			uni.navigateTo({
				url: '../index_malaInfo/index_malaInfo'
			});
		},
		toSearch() {
			uni.navigateTo({
				url: '../Search/Search'
			});
		},
		//轮播图
		change(e) {
			this.current = e.detail.current;
		}
	}
}
</script>

<style>
.container {
	padding: 0 40rpx;
}

.container .top {
	display: flex;
	justify-content: space-between;
}

.container .top view:nth-child(2) {
	margin-left: 400rpx;
}

.container .Search {
	margin-top: 40rpx;
}

.container .sheng {
	margin-top: 40rpx;
}

.container .xunlian {
	color: #334154;
	margin-top: 20rpx;
}

.container .xunList {
	display: flex;
	justify-content: space-around;
	margin-top: 20rpx;
}
</style>