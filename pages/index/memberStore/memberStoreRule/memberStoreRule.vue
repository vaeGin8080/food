<template>
	<view class="wrap" :style="{ height: height }">
		<scroll-view scroll-y :style="{ height: height }">
			<view class="banner" :style="{ background: `url(${statics.$memberStoreRule}) no-repeat`, backgroundSize: 'contain' }"></view>
			<view class="banner-content">
				<view>
					<view class="flex align-center justify-center">
						<view class="title"><text>会员积分</text></view>
					</view>
					<view class="rule-item">
						<view>1、可通过做任务获得积分，具体积分请以活动为准</view>
						<view>2、消费得积分（限储值卡、微信支付）：</view>
						<view>VIP1红卡会员每消费10元（不足10元不积分）积10积分；</view>
						<view>VIP2 银卡会员每消费10元（不足10元不积分）积16积分；</view>
						<view>VIP3 金卡会员每消费10元（不足10元不积分）积22积分；</view>
						<view>VIP4 黑卡会员每消费10元（不足10元不积分）积30积分；</view>
					</view>
				</view>
				<view>
					<view class="flex align-center justify-center">
						<view class="title"><text>过期积分</text></view>
					</view>
					<view class="rule-item">
						<view class="gl">积分有效期1年</view>
						<view>采用月度滚动过期制，每个自然月的第一天00:00分自动清零已满一年的积分</view>
						<view class="gl">举例说明</view>
						<view>2020年5月1日开始清除2019年4月30日前获得的一年及以上的有效积分，2020年6月1日开始清除2019年5月1日-5月31日间获得的有效积分，以此类推</view>
					</view>
				</view>
			</view>
		</scroll-view>
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
	background-color: #5625ff;
}
.banner {
	position: relative;
	height: 100%;
}
.banner-content {
	position: absolute;
	top: 650rpx;
	left: 0;
	width: 100%;
	color: white;
	background-color: #5625ff;
}
.title {
	width: 450rpx;
	background: url(../../../../static/img/member-rule-zs.png) no-repeat;
	background-size: 100% 100%;
	padding: 0 20rpx;
	text-align: center;
	font-size: 33rpx;
	margin-top: 30rpx;
}
.rule-item {
	margin: 20rpx 30rpx;
	padding: 34rpx 17rpx 20rpx;
	background: rgba(27, 27, 27, 0.2);
	border-radius: 11rpx;
	font-size: 25rpx;
	view {
		margin-bottom: 10rpx;
	}
	.gl {
		color: #e5db38;
	}
}
</style>
