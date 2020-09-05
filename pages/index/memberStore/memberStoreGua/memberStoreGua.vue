<template>
	<view class="wrap">
		<image class="guabg" mode="aspectFill" :src="statics.$memberStoreGua"></image>
		<view class="gua-wrap">
			<view class="jiang-content">
				<view v-if="!isGua" class="jiang-bg flex-ali flex-direction">
					<view class="btn flex-ali" @click="isGua = !isGua"><text>点我刮奖</text></view>
					<view class="day-c flex-ali">
						<text>20</text>
						<text>积分/每次</text>
					</view>
				</view>
				<view v-else class="jiang flex-ali"><text>谢谢惠顾</text></view>
			</view>
			<view>
				<view class="j-title flex-ali">
					<view class="title-bg flex-ali">奖品说明</view>
					<text class="my-jiang" @click="goMy">我的奖品</text>
				</view>
				<memberGuaItem :List="list"></memberGuaItem>
			</view>
			<view class="u-margin-top-40 u-margin-bottom-40">
				<view class="j-title flex-ali"><view class="title-bg flex-ali">活动说明</view></view>
				<view class="p-w">
					<p>1.每次刮奖需要消耗20积分.</p>
					<p>
						2.活动中奖后需要按照规定时间点击
						<text>领奖按钮</text>
						获得实物商品的用户填写正确的联系方式。
					</p>
					<p>3.活动最终解释权归会员伴侣所有</p>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import statics from '@/staticBG.js';
import memberGuaItem from './memberGuatem.vue';
export default {
	components: { memberGuaItem },
	data() {
		return {
			statics,
			isGua: false,
			list: [
				{
					title: '10元优惠券',
					desc: '满69减10优惠劵',
					type: 1,
					price: 10,
					time: '2020.04.16-2020'
				},
				{
					title: '1-999积分',
					desc: '1-999区间内随机刮出',
					type: 2,
					price: '1-999',
					time: '2020.04.16-2020'
				},
				{
					title: '精美礼品',
					desc: '具体奖品请以实物为准',
					type: 3,
					time: '2020.04.16-2020'
				}
			]
		};
	},
	methods: {
		goMy() {
			uni.navigateTo({
				url: '/pages/index/memberStore/memberStoreGua/memberStoreMyJiang/memberStoreMyJiang'
			})
		}
	}
};
</script>

<style lang="scss" scoped>
.wrap {
	background-color: #f40008;
	.guabg {
		width: 100%;
		height: 365rpx;
	}
	.gua-wrap {
		padding: 20rpx;
		.jiang-content {
			margin-top: 10rpx;
			height: 321rpx;
			.jiang {
				background-color: white;
				height: 100%;
			}
			.jiang-bg {
				height: 100%;
				background: url(@/static/img/guajiang-bg.png) no-repeat center;
				background-size: cover;
				.btn {
					width: 322rpx;
					height: 72rpx;
					background: $color;
					border-radius: 11px;
					margin-bottom: 44rpx;
					color: white;
					font-size: 29rpx;
				}
				.day-c {
					text {
						&:first-child {
							display: inline-block;
							margin-top: 4rpx;
							color: $color;
						}
						color: #333333;
						font-size: 22rpx;
					}
				}
			}
		}
	}
	.j-title {
		margin: 20rpx 0;
		position: relative;
		.my-jiang {
			position: absolute;
			right: 0;
			top: 6rpx;
			color: white;
			font-size: 22rpx;
		}
	}
	.title-bg {
		width: 295rpx;
		height: 40rpx;
		background: url(@/static/img/jiang-title-bg.png) no-repeat center;
		background-size: contain;
		color: #feebc5;
		font-size: 33rpx;
	}
	.p-w {
		p {
			font-size: 22rpx;
			color: white;
			line-height: 50rpx;
			text {
				color: #fdeb73;
				font-size: 26rpx;
			}
		}
	}
}
</style>
