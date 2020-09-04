<template>
	<view class="wrap" :style="{ height: height }">
		<view class="banner" :style="{ background: `url(${statics.$memberBirthday})`, backgroundSize: 'cover' }">
			<view class="banner-content">
				<view class="flex align-center justify-center">
					<view class="cir flex align-center">
						<view class="line left"></view>
						<text class="ball"></text>
					</view>
					<text class="fl">生日福利</text>
					<view class="cir flex align-center">
						<text class="ball"></text>
						<view class="line right"></view>
					</view>
				</view>
				<view class="birth-desc flex flex-direction">
					<text>1、生日月双倍积分</text>
					<text>2、生日当天凭证件抵150元消费</text>
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
	background-color: #6a38e8;
}
.banner {
	position: relative;
	height: 846rpx;
	.banner-content {
		position: absolute;
		bottom: 30rpx;
		left: 0;
		width: 100%;
		color: white;
		.fl {
			display: inline-block;
			width: 217rpx;
			height: 45rpx;
			background: #ec1656;
			border-radius: 23rpx;
			text-align: center;
			line-height: 45rpx;
			color: 30rpx;
			margin: 0 30rpx;
		}
		.cir {
			.line {
				width: 134rpx;
				height: 4rpx;
			}
			.left {
				background: linear-gradient(90deg, #6a38e8, #ffb400, #ff5612);
			}
			.right {
				background: linear-gradient(90deg, #ff5612,#ffb400,#6a38e8);
			}
			.ball {
				display: inline-block;
				width: 11rpx;
				height: 11rpx;
				background: #ff5612;
				border-radius: 50%;
			}
		}
	}
}
.birth-desc {
	padding-top: 60rpx;
	font-size: 26rpx;
	color: white;
	padding-left: 48rpx;
	text {
		margin-bottom: 10rpx;
	}
}
</style>
