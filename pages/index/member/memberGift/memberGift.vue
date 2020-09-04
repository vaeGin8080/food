<template>
	<view class="wrap" :style="{ height: height }">
		<view class="banner" :style="{ background: `url(${statics.$memberUpdate}) no-repeat top`, backgroundSize: 'cover' }">
			<view class="banner-content">
				<h1>升级奖励</h1>
				<view class="banner-block flex flex-direction align-center justify-center">
					<h2>升级送积分</h2>
					<text>
						Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Quis ipsum suspendisse ultrices
						gravida. Risus commodo viverra maecenas accumsan lacus vel facilisis.
					</text>
				</view>
				<view class="banner-block flex flex-direction align-center justify-center">
					<h2>奖励二</h2>
					<text>
						Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Quis ipsum suspendisse ultrices
						gravida. Risus commodo viverra maecenas accumsan lacus vel facilisis.
					</text>
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
	background-color: #1E1F3A;
}
.banner {
	position: relative;
	height: 100%;
	.banner-content {
		position: absolute;
		top: 25%;
		left: 0;
		width: 100%;
		color: white;
		padding: 0 44rpx;
		.banner-block {
			margin-bottom: 55rpx;
		}
		h1 {
			color: #FD602B;
			text-align: center;
			font-size: 88rpx;
			margin-bottom: 55rpx;
		}
		h2 {
			margin-bottom: 20rpx;
			color: #fefcfb;
			font-size: 43rpx;
		}
		text {
			font-size: 26rpx;
			color: #fefcfb;
			line-height: 35rpx;
		}
	}
}
</style>
