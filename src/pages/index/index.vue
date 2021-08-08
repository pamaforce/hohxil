<template>
	<view>
		<view class="u-text-center">主页暂未开发</view>
		<button type='primary' plain="true" @tap="navigateTo">跳转至详情页（测试）</button>
		<u-tabbar :list="list"></u-tabbar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						iconPath: "home",
						selectedIconPath: "home-fill",
						text: "主页",
						pagePath: "/pages/index/index",
					},
					{
						iconPath: "/static/guide.png",
						selectedIconPath: "/static/guide-fill.png",
						text: "导览",
						pagePath: "/pages/guide/index",
					},
				],
			};
		},
		onLoad() {},
		methods: {
			navigateTo() {
				uni.navigateTo({
					url: '../station/sndj_station'
				});
			}
		},
	};
</script>

<style lang="scss">
    /deep/button {
        margin-top: 30rpx;
		width: 60%;
		font-size: 35rpx !important;
    }
</style>
