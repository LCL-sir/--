<template>
	<view>
		<view class="page-body">
			<view class="page-section page-section-gap">
				<map :latitude="latitude" :longitude="longitude" :markers="covers">
				</map>
				<img src="static/image/runbu/point.png" class="mapImg">
			</view>
		</view>
		<view class="bottom">
			<view>
				<view class="shu">{{ runTime }}</view>
				<view class="zhong">时间</view>
			</view>
			<view class="runBottom">
				<img src="static/image/runbu/runOn.png" @click="stopRun()">
			</view>
			<view>
				<view class="shu">0.0Km</view>
				<view class="zhong">公里</view>
			</view>
		</view>
		<view class="fan" @click="torunbu()">
			<img src="static/image/runbu/fanhui.png" alt="">
		</view>
		<uni-popup ref="popup" type="bottom">
			<view class="tan">
				<view class="xian"></view>
				<view class="pao">跑步轨迹</view>
				<view class="info">
					<view>
						<img src="static/image/runbu/info1.png" alt="">
						<view>{{ sTime }}</view>
						<view>时间</view>
					</view>
					<view>
						<img src="static/image/runbu/info2.png" alt="">
						<view>0.00km</view>
						<view>公里</view>
					</view>
				</view>
				<view class="map">
					<map style="width: 100%; height: 100vh;" :latitude="latitude" :longitude="longitude" :markers="covers">
					</map>
					<img src="static/image/runbu/point.png" alt="">
				</view>
				<view class="runBottom bBottom">
					<img src="static/image/runbu/jieshu.png" @click="close()">
				</view>
			</view>
		</uni-popup>
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
				iconPath: 'static/location.png'
			}, {
				latitude: 39.90,
				longitude: 116.39,
				iconPath: 'static/location.png'
			}],
			runTime: "0:00:00",
			sTime: null
		}
	},
	onLoad() {
		this.getMapGPS();
		this.runTimefun();
	},
	methods: {
		// 获取位置
		getMapGPS() {
			console.log("获取位置");
			// uni.getLocation({
			// 	type: 'wgs84',
			// 	success: function (res) {
			// 		console.log('当前位置的经度：' + res.longitude);
			// 		console.log('当前位置的纬度：' + res.latitude);
			// 	},
			// 	complete: function (res) {
			// 		console.log(res);
			// 	}
			// });
		},
		stopRun() {
			this.$refs.popup.open('bottom')
			this.sTime = this.runTime;
		},
		runTimefun() {

			// 设置初始时间为 0:00:00
			let hours = 0;
			let minutes = 0;
			let seconds = 0;

			// 每秒更新时间，并更新显示在页面上
			setInterval(() => {
				// 增加一秒
				seconds++;
				// 如果秒数等于 60，则增加一分钟，并将秒数重置为 0
				if (seconds === 60) {
					minutes++;
					seconds = 0;
				}
				// 如果分钟数等于 60，则增加一小时，并将分钟数重置为 0
				if (minutes === 60) {
					hours++;
					minutes = 0;
				}
				// 将时间转换为字符串格式，并更新页面上的元素
				const timeString = `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
				// console.log(timeString)
				this.runTime = timeString;
			}, 1000);
		},
		close() {
			this.$refs.popup.close()
		},
		torunbu() {
			uni.switchTab({
				url: '../runbu/runbu'
			});
		}
	}
}
</script>

<style>
uni-map {
	height: 85vh !important;
	width: 100VW;
}

.mapImg {
	position: relative;
	top: -600rpx;
	left: 300rpx;
}

.bottom {
	position: relative;
	bottom: 440rpx;
	left: 0;
	width: 100vw;
	height: 400rpx;
	background-color: #FFFFFF;
	border-radius: 40rpx 40rpx 0 0;
	display: flex;
	justify-content: space-evenly;
	align-items: center;
	float: left;
	z-index: 999;
}

.bottom .runBottom {
	width: 200rpx;
	height: 200rpx;
	background-color: #6C5DD3;
	border-radius: 80rpx;
}

.bottom .runBottom img {
	margin: 50rpx;
}

.bottom .shu {
	font-size: 52rpx;
}

.bottom .zhong {
	text-align: center;
}

.tan {
	width: 100%;
	height: 90vh;
	background-color: #FFFFFF;
	border-radius: 48rpx 48rpx 0 0;
	padding: 0 40rpx 0 40rpx;
	box-sizing: border-box;
}

.tan .xian {
	width: 130rpx;
	height: 6rpx;
	background-color: #E5E6EC;
	position: relative;
	top: 20rpx;
	left: 292rpx;
	border-radius: 12rpx;
}

.tan .pao {
	font-size: 40rpx;
	position: relative;
	top: 60rpx;
}

.tan .info {
	display: flex;
	justify-content: space-evenly;
	position: relative;
	top: 128rpx;
	font-size: 40rpx;
}

.tan .info>view {
	/* background-color: #6C5DD3; */
	width: 45%;
	height: 320rpx;
	border-radius: 16px;
	box-shadow: 6px 6px 10px #bababa,
		-6px -6px 49px #ffffff;

}

.tan .info>view view {
	margin-left: 40rpx;
}

.tan .info>view view:nth-child(3) {
	font-size: 16px;
}

.tan .map {
	width: 308px;
	height: 195px;
	overflow: hidden;
	position: relative;
	top: 83px;
	border-radius: 20px;
	margin: 0 auto;
}

.tan .map img {
	position: relative;
	top: -990rpx;
	left: 200rpx;
}

.tan .bBottom {
	position: relative;
	top: 98px;
	left: 115px;
}

.tan .bBottom img {
	position: relative;
	top: 13px;
	left: 16px;
}

.fan {
	float: left;
	position: relative;
	left: -32rpx;
	top: -1740rpx;
}
</style>