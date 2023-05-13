<template>
	<view>
		<view class="uni-padding-wrap uni-common-mt">
			<view>
				<video id="myVideo" src="../../static/video/video1.mp4" @error="videoErrorCallback" :danmu-list="danmuList"
					enable-danmu danmu-btn controls autoplay="true"></video>
			</view>
			<!-- #ifndef MP-ALIPAY -->
			<view class="haokan">
				<view class="xian"></view>
				<view class="uni-list uni-common-mt weizhi">
					<view class="uni-list-cell">
						<view>
							<view class="uni-label">请发送友好弹幕</view>
						</view>
						<view class="uni-list-cell-db">
							<input v-model="danmuValue" class="uni-input" type="text" placeholder="在此处输入弹幕内容" />
						</view>
					</view>
				</view>
				<view class="uni-btn-v">
					<button @click="sendDanmu" class="page-body-button">发送弹幕</button>
				</view>
			</view>
			<!-- #endif -->
		</view>
	</view>
</template>


<script>
	export default {
		data() {
			return {
				src: '',
				danmuList: [{
						text: '大家一起加油',
						color: '#ff0000',
						time: 1
					},
					{
						text: '加油',
						color: '#ff00ff',
						time: 3
					}
				],
				danmuValue: ''
			}
		},
		onReady: function(res) {
			// #ifndef MP-ALIPAY
			this.videoContext = uni.createVideoContext('myVideo')
			// #endif
		},
		methods: {
			sendDanmu: function() {
				this.videoContext.sendDanmu({
					text: this.danmuValue,
					color: this.getRandomColor()
				});
				this.danmuValue = '';
			},
			videoErrorCallback: function(e) {
				uni.showModal({
					content: e.target.errMsg,
					showCancel: false
				})
			},
			getRandomColor: function() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				return '#' + rgb.join('')
			}
		}
	}
</script>


<style>
	#myVideo {
		width: 100vw;
	}

	.haokan {
		box-shadow: 0px -20px 60px #d9d9d9, 20px 20px 60px #ffffff;
		position: relative;
		top: 450rpx;
		border-radius: 40rpx 40rpx 0 0;
		padding-top: 40rpx;
		height: 296rpx;
	}

	.haokan .xian {
		width: 100px;
		height: 5px;
		background-color: #E5E6EC;
		position: relative;
		top: -22rpx;
		left: 274rpx;
		border-radius: 6px;

	}

	.uni-btn-v button {
		margin-top: 20rpx;
		background-color: #6C5DD3;
		color: #ffffff;
	}
</style>