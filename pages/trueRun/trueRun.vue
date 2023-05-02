<template>
	<view>
		<view class="page-body">
			<view class="page-section page-section-gap">
				<map style="width: 100%; height: 100vh;" :latitude="latitude" :longitude="longitude" :markers="covers">
				</map>
			</view>
		</view>
		<view class="bottom">
			<view>
				<view>0:34:11</view>
				<view>时间</view>
			</view>
			<view class="runBottom">
				<img src="../../static/image/runbu/runOn.png" alt="">
			</view>
			<view>
				<view>3.0Km</view>
				<view>公里</view>
			</view>
		</view>
	</view>
</template>


<script>
	export default {
		data() {
			return {
				id: 0,
				title: 'map',
				latitude: 39.909,
				longitude: 116.39742,
				covers: [{
					latitude: 39.909,
					longitude: 116.39742,
					iconPath: '../../../static/location.png'
				}, {
					latitude: 39.90,
					longitude: 116.39,
					iconPath: '../../../static/location.png'
				}]
			}
		},
		onLoad() {
			this.getMapGPS();
		},
		methods: {
			// 获取位置
			getMapGPS(){
				console.log("获取位置");
				uni.getLocation({
					type: 'wgs84',
					success: function (res) {
						console.log('当前位置的经度：' + res.longitude);
						console.log('当前位置的纬度：' + res.latitude);
					},
					complete:function(res){
						console.log(res);
					}
				});
			}
		}
	}
</script>

<style>
	.page-body {
		
	}
	.bottom {
		position: relative;
		bottom: 440rpx;
		left: 0;
		width: 100vw;
		height: 360rpx;
		background-color: #FFFFFF;
		border-radius: 40rpx 40rpx 0 0;
		display: flex;
		justify-content: space-evenly;
    align-items: center;
	}
.bottom .runBottom{
	width: 200rpx;
	height: 200rpx;
	background-color: #6C5DD3;
	border-radius: 80rpx;
}
.bottom .runBottom img {
	margin: 50rpx;
}
.bottom view view:nth-child(1) {
	font-size: 52rpx;
}
.bottom view view:nth-child(2) {
	text-align: center;
}
</style>