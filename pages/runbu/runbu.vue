<template>
	<view class="container">
		<view class="top">
			<view :class="{ botStyle1: sexStyleValue == 1 }" @click="changebot(1)">运动</view>
			<view :class="{ botStyle1: sexStyleValue == 2 }" @click="changebot(2)">记录</view>
		</view>
		<view class="main">
			<view class="main_left" v-if="sexStyleValue == 1">
				<view @click="open">
					{{ runbuTypeValue[runbuType] }} or
				</view>
				<view>
					<uni-popup ref="popup" type="bottom" background-color="#FFFFFF">
						<view class="tan">
							<view>
								<view :class="{ tan3: runbuType == 1 }" @click="rundongtai(1)">
									<img src="../../static/image/runbu/2.png" alt="">
								</view>
								<span>跑步</span>
							</view>
							<view>
								<view :class="{ tan3: runbuType == 2 }" @click="rundongtai(2)">
									<img src="../../static/image/runbu/1.png" alt="">
								</view>
								<span>健走</span>
							</view>
							<view>
								<view :class="{ tan3: runbuType == 3 }" @click="rundongtai(3)">
									<img src="../../static/image/runbu/3.png" alt="">
								</view>
								<span>骑行</span>
							</view>
						</view>
						<view class="off" @click="close()">
							<img src="../../static/image/runbu/X.png" alt="">
						</view>
					</uni-popup>
				</view>
				<view class="sun">
					<view class="sun_left">
						<view>
							<view></view>
							<view>累计跑步</view>
						</view>
						<view class="sunNumber">5.25</view>
						<view class="sunlu">公里</view>
					</view>
					<view class="sun_right">
						<view>
							<view></view>
							<view>本周跑步</view>
						</view>
						<view class="sunNumber">24.37</view>
						<view class="sunlu">公里</view>
					</view>
				</view>
				<view class="run" @click="toTimeOut()">
					{{ runbuTypeValue[runbuType] }}
				</view>
			</view>
			<view class="main_right" v-if="sexStyleValue == 2">
				<view class="right_top">
					<view class="runSun">
						<view>0.00</view>
						<view>公里</view>
					</view>
					<view class="runren">
						<img src="../../static/image/runbu/jilurun.png" alt="">
					</view>
				</view>
				<view class="jiluka">
					<view class="jiluka1">
						<view>
							<view class="jiluNumber">0.00km</view>
							<view>累计跑量</view>
						</view>
						<view>
							<view class="jiluNumber">0.00小时</view>
							<view>总时长</view>
						</view>
						<view>
							<view class="jiluNumber">0大卡</view>
							<view>总消耗</view>
						</view>
					</view>
					<view class="jiluka2">
						<view>
							<view class="jiluNumber">0.00km</view>
							<view>平均跑量</view>
						</view>
						<view>
							<view class="jiluNumber">0'00"</view>
							<view>平均倍速</view>
						</view>
						<view>
							<view class="jiluNumber">0天</view>
							<view>最长续航</view>
						</view>
					</view>
				</view>
				<view class="xian"></view>
				<view class="bottomTitle">加油！快去跑一次步吧~</view>
			</view>
		</view>

	</view>
</template>

<script>
export default {
	data() {
		return {
			// 选中状态
			sexStyleValue: 1,
			//弹出运动状态
			runbuType: 1,
			runbuTypeValue: ["", "跑步", "健走", "骑行"]
		}
	},
	onLoad(options) {

	},
	onShow() {

	},
	methods: {
		// 选择运动 / 记录
		changebot(e) {
			if (e == 1) {
				if (this.sexStyleValue == 1) {
					this.sexStyleValue = 0
				} else {
					this.sexStyleValue = 1;
				}
			}
			if (e == 2) {
				if (this.sexStyleValue == 2) {
					this.sexStyleValue = 0
				} else {
					this.sexStyleValue = 2;
				}
			}
		},
		// 打开遮罩层
		open() {
			this.$refs.popup.open('center')
		},
		// 关闭遮罩层
		close() {
			this.$refs.popup.close()
		},
		// 弹出运动状态
		rundongtai(e) {
			switch (e) {
				case 1:
					if (this.runbuType == 1) {
						this.runbuType = 0
					} else {
						this.runbuType = 1;
					}
					break;
				case 2:
					if (this.runbuType == 2) {
						this.runbuType = 0
					} else {
						this.runbuType = 2;
					}
					break;
				case 3:
					if (this.runbuType == 3) {
						this.runbuType = 0
					} else {
						this.runbuType = 3;
					}
					break;
			}
		},
		toTimeOut() {
			uni.navigateTo({
				url: '../countdown/countdown'
			});
		}
	},
}
</script>

<style lang="scss" scoped>
.top {
	display: flex;
	justify-content: space-evenly;
	padding: 40rpx 30rpx;
}

.main .main_left:nth-child(1) {
	background-color: #6C5DD3;
	width: 160rpx;
	height: 64rpx;
	color: #FFFFFF;
	border-radius: 18rpx;
	text-align: center;
	margin-left: 60rpx;
	line-height: 64rpx;
}

>>>.uni-popup .uni-popup__wrapper {
	border-radius: 50rpx;
}

.main_left .tan {
	width: 89vw;
	height: 340rpx;
	background-color: #FFFFFF;
	border-radius: 50rpx;
	display: flex;
	justify-content: space-evenly;
	align-items: center;
}

.main_left .tan view view {
	width: 140rpx;
	height: 140rpx;
	background-color: #DCDFE3;
	text-align: center;
	line-height: 200rpx;
	border-radius: 36rpx;
}

.main_left .tan view span {
	color: #000000;
}

.botStyle1 {
	border-bottom: 2px solid #6C5DD3;
}

.tan3 {
	background-color: #6C5DD3 !important;
}

.off {
	position: absolute;
	bottom: -332rpx;
	left: 246rpx;
}

.sun {
	display: flex;
	justify-content: space-evenly;
	width: 100vw;
	position: absolute;
	left: 0;
	top: 246rpx;
}

.sun>view {
	width: 300rpx;
	height: 300rpx;
	background-color: #5DD8D0;
	border-radius: 40rpx;
}

.sun .sun_left view view:nth-child(1) {
	background-color: #6C5DD3;
	width: 14rpx;
	height: 50rpx;
	position: absolute;
	top: 40rpx;
	left: 90rpx;
}

.sun .sun_left view view:nth-child(2) {

	position: absolute;
	top: 34rpx;
	left: 120rpx;
}

.sun .sun_left .sunNumber {
	color: #000000;
	font-size: 80rpx;
	position: absolute;
	top: 126rpx;
	left: 114rpx;
}

.sun .sun_left .sunlu {
	color: #000000;
	position: absolute;
	left: 222rpx;
	top: 208rpx;
	font-size: 48rpx;
}



.sun .sun_right view view:nth-child(1) {
	background-color: #6C5DD3;
	width: 14rpx;
	height: 50rpx;
	position: absolute;
	top: 40rpx;
	left: 444rpx;
}

.sun .sun_right view view:nth-child(2) {

	position: absolute;
	top: 34rpx;
	left: 476rpx;
}

.sun .sun_right .sunNumber {
	color: #000000;
	font-size: 80rpx;
	position: absolute;
	top: 126rpx;
	left: 454rpx;
}

.sun .sun_right .sunlu {
	color: #000000;
	position: absolute;
	left: 564rpx;
	top: 208rpx;
	font-size: 48rpx;
}


.run {
	background-color: #6C5DD3;
	width: 200rpx;
	height: 200rpx;
	border-radius: 40rpx;
	text-align: center;
	line-height: 200rpx;
	font-size: 32rpx;
	position: absolute;
	bottom: 88rpx;
	left: 268rpx;
}

.right_top {
	height: 270rpx;
}

.runSun {
	margin-left: 76rpx;
}

.runSun>view:nth-child(1) {
	font-size: 80rpx;
}

.runSun>view:nth-child(2) {
	margin-left: 71px;
	font-size: 21px;
}

.runren {
	position: relative;
	left: 432rpx;
	top: -154rpx;
}

.jiluka {
	height: 420rpx;
	margin: 0 56rpx;
	border-radius: 50rpx;
	background: url(../../static/image/runbu/bg.png) no-repeat 45% 54%;
	display: flex;
	justify-content: space-evenly;
	flex-direction: column;
}

.jiluka .jiluka1,
.jiluka .jiluka2 {
	display: flex;
	justify-content: space-around
}

.jiluka .jiluka1 .jiluNumber,
.jiluka .jiluka2 .jiluNumber {
	font-size: 40rpx;
}

.xian {
	width: 100vw;
	height: 16rpx;
	margin-top: 28rpx;
	background-color: #dcdfe3;
}

.bottomTitle {
	text-align: center;
	margin-top: 72rpx;
	font-size: 36rpx;
}
</style>
