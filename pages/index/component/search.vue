<template>
	<view>
	<!--定位-->
		<view class="seach-view">
			<image src="../../../static/coen/dingwei.svg" mode="widthFix"></image>
			<text class="seach-text">阿里巴巴西溪园区</text>
			<text>></text>
		</view>
		<!--搜索-->	
		<view class="search-cont">
			<view class="search" @click="seaRch()">
				<image src="../../../static/coen/sousuo.svg" mode="widthFix" class="search-img"></image>
				<input type="text" placeholder="麻辣烫" disabled />
			</view>
		</view>
		<!--自定义轮播-->
		<view>
			<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item>
					<view class="swiper-item uni-bg-red">A</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-green">B</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-blue">C</view>
				</swiper-item>
			</swiper>
		</view>
		
	</view>
</template>

<script>
</script>

<style scoped>
	.seach-view image {width: 35upx; height: 35upx;}
	.seach-view {font-size: 30upx; font-weight: bold; display: flex; text-align: center;}
	.seach-text {padding: 0 10upx;}
	
	.search-img {
		margin: auto 0 auto 20upx;
		width: 40upx;
		height: 40upx;
	}
	
	.search {
		height: 70upx;
		line-height: 70upx;
		width: 100%;
		display: flex;
		flex-direction: flex;
		background: #eff3f4;
		border-radius: 10rpx;
	}
	
	.search input {
		height: 70upx;
		line-height: 70upx;
		width: 100%;
		font-size: 25upx;
		color: #666666;
	}
	
	.search-cont {
		display: flex;
		justify-content: space-between;
		height: 70upx;
		align-items: center;
	}
</style>
