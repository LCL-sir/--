<template>
	<view class="container">
		<view class="top">
			<view class="topTitle">社区</view>
			<view class="topUser">
				<view v-for="(item, index) in  userList" :key="index" @click="pinglun(item)">
					<img :src="item">
				</view>
			</view>
		</view>
		<view class="mian">
			<view class="mainList" v-for="(item, index) in PLList" :key="index">
				<view>
					<img :src="item.userImg" alt="" class="userBook">
					<view class="userName">{{ item.name }}</view>
					<view class="upTime">{{ item.outTime }}</view>
				</view>
				<view class="Title">{{ item.title }}</view>
				<view class="hdImg">
					<img :src="item.img" alt="">
				</view>
				<view class="botList">
					<view>
						<img src="static/image/square/live.png" @click="botLive(item)">
						{{ item.live }}
					</view>
					<view>
						<img src="static/image/square/pl.png" >
						{{ item.pl }}
					</view>
					<view>
						<img src="static/image/square/fx.png" @click="fenxiang(item)">
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			userList: ["static/image/square/addUser.png", "static/image/square/list1.png", "static/image/square/list2.png", "static/image/square/list3.png", "static/image/square/list4.png"],
			PLList: [{
				id: 0,
				name: "Emily Cooper",
				userImg: "static/image/square/userimg.png",
				outTime: "34秒前",
				title: "让我们一起加入吧！ ",
				img: "static/image/square/Card.png",
				live: 1,
				pl: 0
			},
			{
				id: 1,
				name: "Emily Cooper",
				userImg: "static/image/square/userimg.png",
				outTime: "34秒前",
				title: "让我们一起加入吧！ ",
				img: "static/image/square/Card.png",
				live: 1,
				pl: 0
			}],
			botClickNumber: 0
		}
	},
	onLoad(options) {

	},
	onShow() {

	},
	methods: {
		// 点击小红心
		botLive(e) {
			if (this.botClickNumber == 0) {
				this.botClickNumber = 1;
				this.PLList[e.id].live += 1;
				return
			}
			if (this.botClickNumber == 1) {
				this.botClickNumber = 0;
				this.PLList[e.id].live -= 1;
				return
			}
		},
		//点击分享
		fenxiang(e) {
			
		},
		// 点击评论
		pinglun(){
			uni.navigateTo({
				url: '../youpinglun/youpinglun'
			});
		}
	},
}
</script>

<style lang="scss" scoped>
.topTitle {
	margin-left: 40rpx;
	margin-top: 40rpx;
	font-size: 40rpx;
	color: #707070;
}

.topUser {
	display: flex;
	justify-content: space-evenly;
	margin-top: 40rpx;
}

.mainList {
	width: 87vw;
	height: 700rpx;
	margin: 40rpx auto;
	border-radius: 30rpx;
	background: #FFFFFF;
	box-shadow: 40rpx 40rpx 120rpx #d9d9d9, -40rpx -40rpx 120rpx #ffffff;
}

.mainList .userBook {
	margin-left: 40rpx;
	margin-top: 40rpx;
}

.mainList .userName {
	position: relative;
	top: -88rpx;
	left: 134rpx;
}

.mainList .upTime {
	position: relative;
	top: -84rpx;
	left: 132rpx;
	font-size: 28rpx;
	color: #75818F;
}

.mainList .Title {
	margin-left: 44rpx;
	margin-top: -60rpx;
}

.mainList .hdImg {
	text-align: center;
	margin-top: 28rpx;
}

.mainList .botList {
	display: flex;
	justify-content: space-around;
	margin-top: 10rpx;
}

.mainList .botList>view {
	display: flex;
	align-items: center;
}
</style>
