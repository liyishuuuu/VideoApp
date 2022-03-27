<template>
	<view>
		<swiper class="home_swiper" indicator-dots="true" autoplay="true" :interval="2000">
			<swiper-item v-for="i in list" :key="i">
				<view class="swiper-item uni-bg-red">
					<image :src="i" mode="aspectFill"></image>
				</view>
			</swiper-item>
		</swiper>
		<uni-title title1="朝夕名师" title2="在线直播" text1="直播互动学习，感受技术韵律"></uni-title>
		<view class="public-box">
			<view @click="goPublic(i.url, i.text)" v-for="i in publicList" :key="i.id" class="public-list">
				<image :src="i.imgs" mode=""></image>
				<text>{{i.text}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: ["https://cdn.sspai.com/article/42610ec0-c1d6-566b-836e-334cd0aa9b35.jpg?imageMogr2/auto-orient/quality/95/thumbnail/!2880x620r/gravity/Center/crop/2880x620/interlace/1", 
						"https://cdn.sspai.com/article/6216c457-6bf2-5c37-28da-37449ca6731d.png?imageMogr2/auto-orient/quality/95/thumbnail/!2880x620r/gravity/Center/crop/2880x620/interlace/1", 
						"https://cdn.sspai.com/article/1c011188-8dce-e854-0577-14b8736764b6.png?imageMogr2/auto-orient/quality/95/thumbnail/!2880x620r/gravity/Center/crop/2880x620/interlace/1"],
						publicList:[]
			}
		},
		onLoad() {
			uni.request({
			    url: 'https://www.fastmock.site/mock/5a354cf58d48825b6778c186ab1c0501/app/getUserInfo', //仅为示例，并非真实接口地址。
			    success: (res) => {
					this.publicList = res.data.data
			    }
			});
		},
		methods: {
			getTitleFun(text){
				console.log(text)
			},
			goPublic(url, title){
				// console.log(url)
				uni.navigateTo({
				    url: `/pages/publicView/publicView?url=${url}&title=${title}`
				});
			}
		} 
	} 
</script>

<style>
	.swiper-item image{
		width: 100%;
		/* #ifdef MP */
			height: 120px;
		/* #endif */
		/* #ifdef APP-PLUS */
			height: 200px;
		/* #endif */
		
	}
	.public-box,
	.buddy-box {
		display:flex;
		flex-direction: row;
		flex-wrap: wrap;
		align-items: center;
		justify-content: space-between;
		padding: 10px;
	}
	.public-list {
		width: 48%;
		height: 120px;
		margin-bottom: 40px;
		text-align: center;
	}
	.public-list image {
		width: 100%;
		height: 200rpx;
		height: 250rpx;
		margin-bottom: 5px;
	}
	.public-list text {
		font-size: 14px;
		line-height: 20px;
		color: #333;
	}
	.recruitSmall-box {
		padding: 10px;
	}
	.recruitSmall-list {
		display: flex;
		flex-direction: row;
		margin-bottom: 10px;
	}
	.recruitSmall-list image {
		width: 40%;
		height: 100px;
		margin-right: 10px;
		border-radius: 10px;
	}
	.recruitSmall-text-box {
		flex:1;
		display: flex;
		flex-direction: column;
		color: #333;
		font-size: 12px;
	}
	.recruitSmall-text-title {
		font-weight: 600;
		margin: 5px 0;
		font-size: 16px;
	}
	.buddy-box .buddy-list {
		width: 30%;
		height: 60px;
	}
</style>
