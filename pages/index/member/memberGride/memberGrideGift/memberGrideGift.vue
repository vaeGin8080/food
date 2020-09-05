<template>
	<view class="wrap" :style="{ height: height }">
		<view class="banner flex align-center justify-center flex-direction" :style="{ background: `url(${statics.$memberGrideVip}) no-repeat top`, backgroundSize: 'cover' }">
			<view class="logo">logo</view>
			<h2>VIP会员特权</h2>
			<view class="btn flex-ali">
				会员每月领取超值礼券
			</view>
		</view>
		<view class="content">
			<view class="flex align-center justify-center">
				<view class="title flex align-center justify-center">
					<image src="../../../../../static/img/VIP-title-bg-left.png"></image>
					<text class="flex-ali">月度礼卷</text>
					<image src="../../../../../static/img/VIP-title-bg.png"></image>
				</view>
			</view>
			<memerStoreVip :List="monthList"></memerStoreVip>
		</view>
	</view>
</template>

<script>
import Json from '@/Json.js';
import statics from '@/staticBG';
import memerStoreVip from '@/components/memerStoreVip/memerStoreVip.vue'
export default {
	components: { memerStoreVip },
	data() {
		return {
			statics,
			height: '667px',
			monthList: Json.monthList,
		};
	},
	onLoad() {
		let sysheight = uni.getSystemInfoSync().windowHeight;
		this.height = `${sysheight}px`;
	},
	methods: {}
};
</script>

<style lang="scss" scoped>
.wrap {
	background-color: #FFFFFF;
}
.banner {
	position: relative;
	height: 428rpx;
	color: white;
	font-weight: bold;
	.logo {
		font-size: 55rpx;
		margin-bottom: 30rpx;
	}
	h2 {
		margin-bottom: 20rpx;
		color: #FFBF4A;
		font-size: 94rpx;
		margin-bottom: 26rpx;
	}
	.btn {
		width: 495rpx;
		height: 67rpx;
		background: #FFBF4A; 
		border-radius: 33rpx;
	}
}
.title {
	padding: 0 20rpx;
	font-size: 29rpx;
	color: white;
	margin-top: 30rpx;
	margin-bottom: 30rpx;
	image {
		width: 141rpx;
		height: 11rpx;
	}
	text {
		margin: 0 20rpx;
		width: 217rpx;
		height: 45rpx;
		background: #EC1556;
		border-radius: 22rpx;
	}
}
.content {
	padding: 20rpx;
}
</style>
