<template>
	<view class="wrap" :style="{ height: height }" @click.stop="isDown = false">
		<view class="banner" :style="{ background: `url(${statics.$memberStoreMyJf})`, backgroundSize: 'cover' }">
			<u-navbar back-text="积分" back-icon-color="#fff" :background="{ background: '', border: 'none' }" :back-text-style="{ color: '#fff' }"></u-navbar>
			<view class="mx flex align-center justify-end" @click="goRecord">
				<text>兑换记录</text>
				<image src="@/static/img/right-jt-white.png"></image>
			</view>
			<view class="ye flex justify-center align-end">
				<text>1231</text>
				<text>积分</text>
			</view>
		</view>
		<view class="wallet-content">
			<view class="detail-head flex align-center justify-between">
				<text class="head-t">本月</text>
				<view class="head-right">
					<view @click.stop="isDown = !isDown">
						<text>全部</text>
						<u-icon name="arrow-down" color="#666666" size="22"></u-icon>
					</view>
					<view class="dorn" v-if="isDown">
						<view class="dorn-item" v-for="(item,index) in typeList" :key="index" @click.stop="request">
							{{item.label}}
						</view>
					</view>
				</view>
			</view>
			<recordList :List="list"></recordList>
		</view>
	</view>
</template>

<script>
import Json from '@/Json.js';
import statics from '@/staticBG';
import recordList from '@/components/recordList/recordList.vue'
export default {
	components: {recordList},
	data() {
		return {
			statics,
			height: '667px',
			isDown: false,
			list: [
				{ label: '线下消费', time: '2020.4.12 09.15.48', moon: true, money: 56.0 },
				{ label: '退款', time: '2020.4.12 09.15.48', moon: false, money: 156.0 },
				{ label: '查额退款', time: '2020.4.12 09.15.48', moon: false, money: 56.0 },
				{ label: '充值赠送', time: '2020.4.12 09.15.48', moon: false, money: 56.0 }
			],
			typeList: [
				{label: '全部',id:1},
				{label: '获取',id:2},
				{label: '支出',id:3},
			]
		};
	},
	onLoad() {
		let sysheight = uni.getSystemInfoSync().windowHeight;
		this.height = `${sysheight}px`;
	},
	methods: {
		request() {
			this.isDown = false
		},
		goRecord() {
			uni.navigateTo({
				url: '/pages/index/memberStore/memberRecord/memberRecord'
			})
		}
	}
};
</script>

<style lang="scss" scoped>
.wrap {
	height: 100%;
	background-color: white;
}
.banner {
	width: 100%;
	height: 328rpx;
	padding: 30rpx 20rpx;
	.mx {
		text {
			color: #ffffff;
			font-size: 22rpx;
		}
		image {
			width: 16rpx;
			height: 16rpx;
			margin-left: 10rpx;
		}
	}
	.ye {
		margin-top: 20rpx;
		color: #ffffff;
		h2 {
			font-size: 83rpx;
			margin-bottom: 10rpx;
		}
		text {
			&:first-child {
				font-size: 50rpx;
			}
			&:last-child {
				display: inline-block;
				margin-bottom: 10rpx;
				font-size: 22rpx;
			}
		}
	}
}

.wallet-content {
	.detail-head {
		padding: 20rpx 25rpx;
		.head-t {
			color: #666666;
			font-size: 29rpx;
		}
		.head-right {
			width: 146rpx;
			height: 44rpx;
			background: #EEEEEE;
			border-radius: 22rpx;
			text-align: center;
			line-height: 44rpx;
			position: relative;
			text {
				display: inline-block;
				margin-right: 10rpx;
				color: #666666;
				font-size: 26rpx;
			}
			.dorn {
				position: absolute;
				bottom: -190rpx;
				left: 0;
				width: 146rpx;
				z-index: 666;
				background-color: white;
				border: 1rpx solid #DDDDDD;
				padding: 10rpx 0;
				.dorn-item {
					margin: 0 20rpx;
					padding: 5rpx 0;
					border-bottom: 1rpx solid #D0CACB;
					font-size: 29rpx;
					color: #333333;
					&:last-child {
						border-bottom: none;
					}
				}
			}
		}
	}
}
</style>
