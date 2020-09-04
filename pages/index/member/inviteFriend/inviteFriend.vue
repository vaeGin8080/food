<template>
	<view class="wrap" :style="{ height: height }">
		<view class="banner" :style="{ background: `url(${statics.$friendBG}) no-repeat center`, backgroundSize: 'cover' }"></view>
		<view class="banner-content">
			<view>
				<h1>我的邀请</h1>
				<view class="banner-block flex flex-direction align-center justify-center">
					<image src="../../../../static/img/feiendGift.png"></image>
					<text class="yq">邀请好友领奖励，赶快去试试~</text>
					<view class="btn flex-ali">
						<text>立即邀请</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import statics from '@/staticBG';
export default {
	data() {
		return {
			statics,
			height: '667px'
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
	background-color: #FA2A2A;
}
.banner {
	position: relative;
	height: 536rpx;
}
.banner-content {
		position: absolute;
		top: 500rpx;
		left: 0;
		width: calc(100% - 88rpx);
		color: white;
		padding: 28rpx 44rpx 42rpx;
		background-color: #FDF2D5;
		margin: 0 44rpx;
		border-radius: 12rpx;
		.banner-block {
			margin-bottom: 55rpx;
		}
		h1 {
			color: #343434;
			text-align: center;
			font-size: 33rpx;
			margin-bottom: 42rpx;
		}
		image {
			width: 201rpx;
			height: 168rpx;
		}
		.yq {
			display: inline-block;
			font-size: 22rpx;
			color: #B99292;
			margin: 48rpx 0 28rpx;
			line-height: 35rpx;
		}
		.btn {
			width: 425rpx;
			height: 70rpx;
			background: #FA2A2A;
			border-radius: 35rpx;
			color: #F9E74B;
			font-size: 29rpx;
		}
	}
</style>
