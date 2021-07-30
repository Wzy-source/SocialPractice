<template>
	<view class="page">
		<headlogo></headlogo>
		<swiper class="banners" indicator-dots="true" circular="true" autoplay="true" indicator-color="ivory"
			indicator-active-color="#f80">
			<swiper-item v-for="(item, index) in swiperImgList" :key="index">
				<image :src=item mode="scaleToFill"></image>
			</swiper-item>
		</swiper>
		<view class="navigation">
			<view class="navigationTxt">
				<view class="border"></view>
				<view class="borderTxt">快捷导航</view>
			</view>
			<view class="navigationBox">
				<view class="navigationItem" v-for="(item , index) in this.navigationCategoryList" :key="index">
					<view class="navigationImg">
						<image :src="item.link"></image>
					</view>
					<view class="navigationItemTxt">{{item.name}}</view>
				</view>
			</view>
		</view>
		<view class="navigation">
			<view class="navigationTxt">
				<view class="border"></view>
				<view class="borderTxt">最新资讯</view>
			</view>
		</view>
	</view>

</template>

<script>
	import headlogo from "../../component/layout/headlogo.vue"
	export default {
		components: {
			headlogo
		},
		data() {
			return {
				swiperImgList: [],
				navigationCategoryList: [{
						name: "项目简介",
						link: "../../static/icon/navigation/Exhibition.png"
					},
					{
						name: "关于我们",
						link: "../../static/icon/navigation/ourTeam.png"

					},
					{
						name: "宣传内容",
						link: "../../static/icon/navigation/project.png",
					}, {
						name: "成果展示",
						link: "../../static/icon/navigation/propaganda.png"
					},
					{
						name: "实用工具",
						link: "../../static/icon/navigation/userfulTools.png",
					}
				]
			}
		},
		methods: {
			getSwiperImgList() {
				//TODO
				//从后端获取轮播图url以及其他信息
				this.swiperImgList = [
					"https://dss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1092770479,843230546&fm=26&gp=0.jpg",
					"https://res.wx.qq.com/wxdoc/dist/assets/img/0.4cb08bb4.jpg",
					"https://pic.rmb.bdstatic.com/bjh/down/658a6448e983504eac4e1b514a736ec1.jpeg"
				]
			}
		},
		mounted() {
			this.getSwiperImgList();
		}
	}
</script>

<style scoped>
	.page {
		position: absolute;
		left: 0;
		top: 0;
		width: 100%;
		background-color: #F5F5F5;
	}

	.banners swiper-item image {
		width: 100%;
	}

	.banners {
		height: 200px;
	}

	.navigation {
		margin-top: 32rpx;
	}

	.navigationTxt {
		display: flex;
	}

	.border {
		width: 6px;
		border: #F80;
		height: 20px;
		background-color: #F80;
		align-self: center;
	}

	.borderTxt {
		font-size: 20px;
		font-weight: 400;
		align-self: center;
		margin-left: 4px;
	}


	.navigationBox {
		background-color: #FFFFFF;
		height: 160rpx;
		display: flex;
		justify-content: space-between;
		padding-left: 4rpx;
		padding-right: 4rpx;
		box-sizing: border-box;
	}

	.navigationItem {
		height: 140rpx;
		width: 100rpx;
		align-self: center;
		display: flex;
		flex-direction: column;
		justify-content: space-between;

	}

	.navigationImg {
		height: 100rpx;
		width: 100rpx;
	}

	.navigationImg>image {
		height: 100%;
		width: 100%;
	}

	.navigationItemTxt {
		align-self: center;
		font-size: 14rpx;
	}
</style>
