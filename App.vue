<script>
	export default {
		onLaunch: function() {
			// console.log('App Launch')
			const GuideValue = uni.getStorageSync('GuideValue');
			console.log(GuideValue=="")
			if(GuideValue==""){
				// 本地没有缓存数据，进入引导页
				uni.reLaunch({
					// url: './pages/Guide/Guide'
					url: './pages/userInfo/userInfo'
				});
			}
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
</style>
