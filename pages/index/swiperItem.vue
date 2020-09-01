<template>
	<swiper
		class="card-swiper"
		:indicator-dots="false"
		:circular="true"
		:autoplay="true"
		interval="50000"
		duration="1000"
		indicator-color="#8799a3"
		indicator-active-color="#0081ff"
	>
		<swiper-item v-for="(item, index) in List" :key="index">
			<view class="swiper-item">
				<view class="swi-bg h-100" :style="{ backgroundImage: `url(${item.url})`, backgroundSize: 'cover' }">
					<view class="swi-foot flex align-center justify-between">
						<view class="swi-left">
							<view class="shop">
								<text>￥{{ item.price }}</text>
								<text>￥{{ item.orignPrice }}</text>
							</view>
							<view>
								<text class="shop-title">{{ item.title }}</text>
							</view>
						</view>
						<view class="swi-right"><text class="ms">马上抢</text></view>
					</view>
				</view>
			</view>
		</swiper-item>
	</swiper>
</template>

<script>
export default {
	name: 'swiperList',
	props: {
		List: {
			type: Array,
			default() {
				return [];
			}
		}
	}
};
</script>

<style lang="scss" scoped>
.swi-bg {
	position: relative;
	border-radius: 11rpx;
	.swi-foot {
		position: absolute;
		bottom: -80rpx;
		left: 0;
		width: calc(100% - 50rpx);
		height: 125rpx;
		margin: 0 25rpx;
		padding: 0 20rpx;
		background: #ffffff;
		box-shadow: 0px 7px 15px 0px rgba(220, 220, 220, 0.3);
		border-radius: 11rpx;
		.shop {
			margin-bottom: 15rpx;
			text {
				&:first-child {
					color: #fe474f;
					font-size: 30rpx;
					margin-right: 5rpx;
				}
				&:last-child {
					color: #999999;
					font-size: 26rpx;
					text-decoration: line-through;
				}
			}
		}
		.shop-title {
			color: #333333;
			font-size: 30rpx;
			font-weight: 400;
		}
		.ms {
			display: inline-flex;
			justify-content: center;
			align-items: center;
			width: 143rpx;
			height: 44rpx;
			background: #fe474f;
			border-radius: 22px;
			color: white;
			font-size: 25rpx;
		}
	}
}
</style>
