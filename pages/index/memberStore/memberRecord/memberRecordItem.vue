<template>
	<view>
		<view class="shop-item flex flex-direction" v-for="(item, index) in List" :key="index">
			<view class="item-top flex w-100">
				<view class="store-item flex" :style="{ background: `url(${bg}) no-repeat center`, backgroundSize: 'cover' }">
					<view v-if="item.count" class="count">{{ item.count }}张</view>
					<view class="yhj-t flex align-center justify-center"><text>优惠劵</text></view>
					<view class="store-content flex-ali flex-direction">
						<!-- 新人卷 -->
						<view v-if="item.type == 'DISCOUNT'" class="xinren">
							<text>满{{ item.fullPrice }}减{{ item.price }}</text>
						</view>
						<!-- 折扣卷 -->
						<view v-else-if="item.type == 'GIFT'" class="flex-ali flex-direction">
							<h2>{{ item.price }}</h2>
							<text class="mj">满{{ item.fullPrice }}减{{ item.price }}</text>
						</view>
						<!-- 代金券 -->
						<view v-else-if="item.type == 'CASH'" class="flex-ali flex-direction">
							<h2>{{ item.price }}</h2>
							<text class="mj">全场通用</text>
						</view>
					</view>
				</view>
				<view class="shop-content flex flex-direction">
					<h3 class="title">{{item.title}}</h3>
					<text class="type">2020-04-29 13</text>
					<view class="flex align-center justify-between">
						<view class="shop"><text>成功</text></view>
					</view>
				</view>
				<view class="flex align-center">
					<u-icon name="arrow-right" color="#666666" size="22"></u-icon>
				</view>
			</view>
			<view class="item-foot">
				<view class="flex justify-end align-center">
					<text>总价：</text>
					<text class="price">{{item.points}}</text>
					<text>积分</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	props: {
		List: {
			type: Array,
			default() {
				return [];
			}
		}
	},
	data() {
		return {
			bg: require('@/static/img/member-store-juan.png')
		};
	}
};
</script>

<style lang="scss" scoped>
.shop-item {
	background-color: white;
	padding: 20rpx;
	margin-bottom: 20rpx;
	border-radius: 11rpx;
	.store-item {
		width: 219rpx;
		height: 130rpx;
		background-color: white;
		border-radius: 11rpx;
		position: relative;
		.count {
			position: absolute;
			top: 13rpx;
			right: 13rpx;
			width: 43rpx;
			height: 27rpx;
			// background-color: #FFEEE0;
			background: url(@/static/img/member-zhang-bg.png) no-repeat center;
			background-size: cover;
			font-size: 19rpx;
			text-align: center;
			line-height: 27rpx;
			color: #fe6217;
			border-radius: 5rpx;
		}
		.yhj-t {
			width: 40rpx;
			height: 100%;
			text {
				display: inline-block;
				width: 30rpx;
				font-size: 16rpx;
				color: #ffffff;
				margin-left: 20rpx;
			}
		}
		.store-content {
			flex: 1;
			color: white;
			.xinren {
				font-size: 23rpx;
			}
			h2 {
				font-size: 49rpx;
			}
			.mj {
				font-size: 16rpx;
			}
		}
	}
	.shop-content {
		flex: 1;
		padding: 0 16rpx;
		.title {
			color: #1f2f45;
			font-size: 26rpx;
			font-weight: 400;
			@include text-overflow();
		}
		.type {
			display: inline-block;
			margin: 13rpx 0 16rpx;
			color: #999999;
			font-size: 22rpx;
			@include text-overflow();
		}
		.number {
			display: inline-block;
			color: #999999;
			font-size: 22rpx;
			margin-bottom: 13rpx;
		}
		.shop {
			margin-bottom: 15rpx;
			text {
				&:first-child {
					color: #fe474f;
					font-size: 22rpx;
					margin-right: 5rpx;
				}
			}
		}
	}
	.item-top {
		border-bottom: 1rpx solid #DDDDDD;
		padding-bottom: 20rpx;
	}
	.item-foot {
		padding-top: 20rpx;
		text {
			color: #666666;
			font-size: 22rpx;
		}
		.price {
			display: inline-block;
			color: $color;
			font-size: 33rpx;
			margin:  5rpx;
		}
	}

}
</style>
