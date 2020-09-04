<template>
	<view class="wrap">
		<view class="store-head flex align-center justify-between">
			<view class="head-left flex align-center">
				<image src="@/static/img/member-store-monney.png"></image>
				<text>1021</text>
				<u-icon name="arrow-right" color="#FE4850" size="16"></u-icon>
			</view>
			<view class="head-right">
				<text>规则</text>
				<u-icon name="question-circle" color="#666666" size="23"></u-icon>
			</view>
		</view>
		<view class="gk flex flex-direction align-center" :style="{ background: `url(${statics.$memberStoreGj}) no-repeat center`, backgroundSize: 'cover' }">
			<h1 class="gk-ga">刮卡赢大奖</h1>
			<view class="gk-li"><text>众多好礼 唯等你来</text></view>
		</view>
		<view class="store-item">
			<view class="store-top flex align-center justify-between">
				<h2>积分秒杀</h2>
				<view>
					<text class="right-t">距开始仅剩</text>
					<u-icon name="arrow-right" color="#666666" size="22"></u-icon>
				</view>
			</view>
			<view class="ms flex align-center">
				<view class="ms-img flex-ali">
					<h4>VIP1会员</h4>
					<view class="ids">
						<text>324568258009035688</text>
					</view>
				</view>
				<view class="ms-right flex flex-direction justify-between">
					<text class="title">限量兑·格创VIP试用会员</text>
					<view class="flex align-end justify-between">
						<view>
							<view class="shop">
								<text>99积分</text>
								<text>3000积分</text>
							</view>
							<view class="sy"><text>剩余60件</text></view>
						</view>
						<view class="qiang flex-ali"><text>抢</text></view>
					</view>
				</view>
			</view>
		</view>
		<view class="store-item">
			<view class="store-top flex align-center justify-between">
				<h2>积分兑券</h2>
				<view>
					<text class="right-t">查看更多</text>
					<u-icon name="arrow-right" color="#666666" size="22"></u-icon>
				</view>
			</view>
			<memerStoreItem :List="jfList"></memerStoreItem>
		</view>
		<view class="store-item item-two">
			<view class="store-top flex align-center justify-between">
				<h2>礼品兑换</h2>
			</view>
			<memerStoreExchange :List="exChangeList"></memerStoreExchange>
		</view>
		<view class="store-item">
			<view class="store-top flex align-center justify-between">
				<h2>每月领券</h2>
				<view>
					<text class="right-t">查看更多</text>
					<u-icon name="arrow-right" color="#666666" size="22"></u-icon>
				</view>
			</view>
			<memerStoreVip :List="monthList"></memerStoreVip>
		</view>
		<view class="store-item item-two">
			<view class="store-top flex align-center justify-between">
				<h2>商品兑换</h2>
			</view>
			<recommendItem :List="goodsList" :breed="'member'"></recommendItem>
		</view>
	</view>
</template>

<script>
import Json from '@/Json.js';
import statics from '@/staticBG';
import memerStoreItem from './memerStoreItem.vue'
import memerStoreExchange from './memerStoreExchange.vue'
import memerStoreVip from './memerStoreVip.vue'
import recommendItem from '../recommendItem.vue';
export default {
	components: {memerStoreItem,memerStoreExchange,memerStoreVip,recommendItem},
	data() {
		return {
			statics,
			jfList: Json.jfList,
			monthList: Json.monthList,
			exChangeList: Json.swiperList,
			goodsList: Json.swiperList,
		};
	}
};
</script>

<style lang="scss" scoped>
.wrap {
	padding: 22rpx 25rpx;
	.store-head {
		background-color: white;
		padding: 29rpx 20rpx;
		border-radius: 12rpx;
		.head-left {
			image {
				width: 63rpx;
				height: 63rpx;
				margin-right: 18rpx;
			}
			text {
				color: $color;
				font-size: 41rpx;
			}
		}
		.head-right {
			color: #666666;
			font-size: 22rpx;
			text {
				display: inline-block;
				margin-right: 5rpx;
			}
		}
	}
	.gk {
		width: 100%;
		height: 223rpx;
		margin: 18rpx 0;
		padding-top: 20rpx;
		position: relative;
		.gk-ga {
			color: #fdfea5;
			font-size: 84rpx;
		}
		.gk-li {
			position: absolute;
			bottom: 40rpx;
			left: 50%;
			transform: translateX(-50%);
		}
		text {
			color: #f42222;
			font-size: 33rpx;
			font-weight: bold;
		}
	}
}
.store-item {
	padding: 24rpx 20rpx;
	background-color: white;
	margin-bottom: 20rpx;
	border-radius: 12rpx;
	.store-top{
		margin-bottom: 24rpx;
		h2 {
			color: #343434;
			font-size: 29rpx;
		}
	}
	.right-t {
		font-size: 23rpx;
		color: #666666;
	}
	.ms {
		height: 165rpx;
		.ms-img {
			width: 286rpx;
			height: 100%;
			background: url(../../../static/img/member-store-vip.png) no-repeat center;
			background-size: cover;
			position: relative;
			color: white;
			h4 {
				font-size: 27rpx;
			}
			.ids {
				position: absolute;
				left: 0;
				bottom: 14rpx;
				width: 100%;
				text-align: center;
				font-size: 19rpx;
			}
		}
		.ms-right {
			flex: 1;
			height: 100%;
			padding: 5rpx 16rpx;
		}
		.title {
			color: #343434;
			font-size: 26rpx;
		}
		.sy {
			color: #9A9A9A;
			font-size: 19rpx;
		}
		.shop {
			margin-bottom: 10rpx;
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
		.qiang {
			width: 56rpx;
			height: 56rpx;
			background: #9A9A9A;
			border-radius: 50%;
			color: #FFFFFF;
			font-size: 29rpx;
		}
	}
}
.item-two {
	background-color: #F1F1F1;
}
</style>
