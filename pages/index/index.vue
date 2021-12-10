<template>
	<view class="content">
		<u-swiper :height='180' :indicator-dots='true' :autoplay='true' :interval='2500' :duration='500' :list="list1">
		</u-swiper>
		<image src="../../static/half-circle.png" class="image-cover" mode=""></image>
		<view class="btn-group">
			<button type="primary" size="mini" :plain="true" @click="handleGoOtherPage('/pages/feeds/feeds')">精彩动态</button>
			<button type="primary" size="mini" :plain="true" @click="handleGoOtherPage('/pages/me/me')">个人中心</button>
		</view>
		<view class="tab-box">
			<view class="one-nav active">推荐</view>
			<view class="one-nav">资讯</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				list1: [
					'https://cdn.uviewui.com/uview/swiper/swiper1.png',
					'https://cdn.uviewui.com/uview/swiper/swiper2.png',
					'https://cdn.uviewui.com/uview/swiper/swiper3.png',
				]
			}
		},
		onLoad() {

		},
		methods: {
			handleGoOtherPage(url) {
				uni.switchTab({
					url: url
				})
			},

		}
	}
</script>

<style lang="scss" scoped>
	.content {
		display: flex;
		flex-direction: column;
		height: calc(100vh - 50px);
		overflow-y: hidden;

		.image-cover {
			width: 100%;
			height: 100px;
			position: absolute;
			top: 90px;
		}

		.btn-group {
			margin: 0 auto;
			margin-top: -30px;
			display: flex;
			flex-direction: row;

			button {
				background: white;
				margin-left: 10px;
				padding: 3px 40px;
			}
		}

		.tab-box {
			width: 100%;
			height: calc(100vh - 255px);
			background: #f3f3f3;
			margin-top: 25px;
			border-top-left-radius: 20px;
			border-top-right-radius: 20px;
			display: flex;
			justify-content: center;

			.one-nav {
				margin-left: 10px;
				margin-top: -10px;
				color: $uni-text-color;
			}

			.active {
				color: $uni-color-primary;
			}
		}
	}
</style>
