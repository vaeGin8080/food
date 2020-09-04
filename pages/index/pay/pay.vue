<template>
	<view class="wrap">
		<view class="pay">
			<view class="pay-title flex-ali"><text>普通会员</text></view>
			<view class="nav flex align-center justify-around">
				<view class="pay-nav flex align-center flex-direction">
					<text>999</text>
					<text>钱包</text>
				</view>
				<view class="pay-nav flex align-center flex-direction">
					<text>56</text>
					<text>积分</text>
				</view>
			</view>
			<view class="code flex-ali">
				<erCode :val="val"></erCode>
			</view>
			<view class="pay-method">
				<text>其他支付方式</text>
			</view>
			<view class="pay-to flex-ali">
				<text>快速买单</text>
			</view>
		</view>
		<view class="member-bg">
			<image mode="aspectFill" :src="statics.$memberRecharge"></image>
		</view>
	</view>
</template>

<script>
import erCode from '@/components/erCode.vue'
import statics from '@/staticBG';
	export default {
		components: {erCode},
		data() {
			return {
				statics,
				val: 'http://lottery.ydlkeji.com/cpf/tzggao/6392.jhtml'
			};
		}
	}
</script>

<style lang="scss" scoped>
.wrap {
	padding: 25rpx;
	.pay {
		width: 100%;
		background-color: white;
		padding: 30rpx 20rpx;
		.pay-title {
			font-size: 30rpx;
			color: #333333;
		}
	}
	.nav {
		margin-top: 20rpx;
		padding: 30rpx 0;
		.pay-nav {
			text {
				&:first-child {
					color: #FD474F;
					font-size: 34rpx;
					margin-bottom: 20rpx;
				}
				&:last-child {
					color: #656565;
					font-size: 22rpx;
				}
			}
		}
	}
	.code {
		padding: 30rpx 0;
	}
	.pay-method {
		color: #656565;
		font-size: 26rpx;
		margin-bottom: 20rpx;
	}
	.pay-to {
		padding: 10rpx 0;
		text {
			display: inline-flex;
			justify-content: center;
			align-items: center;
			width: 313rpx;
			height: 68rpx;
			border: 2rpx solid #FD474F;
			border-radius: 11rpx;
			color: #FD474F;
			font-size: 26rpx;
		}
		
	}
	.member-bg {
		width: 100%;
		height: 244rpx;
		margin-top: 24rpx;
		image {
			width: 100%;
			height: 100%;
		}
	}
}
</style>
