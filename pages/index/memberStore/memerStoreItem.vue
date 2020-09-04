<template>
	<view class="store flex flex-wrap justify-between">
		<view class="store-block" v-for="(item,index) in List" :key="index">
			<view class="store-item flex" :style="{ background: `url(${bg}) no-repeat center`, backgroundSize: 'cover' }">
				<view v-if="item.count" class="count">
					{{item.count}}张
				</view>
				<view class="yhj-t flex align-center justify-center">
					<text>优惠劵</text>
				</view>
				<view class="store-content flex-ali flex-direction">
					<!-- 新人卷 -->
					<view v-if="item.type == 'DISCOUNT'" class="xinren">
						<text>
							满{{item.fullPrice}}减{{item.price}}
						</text>
					</view>
					<!-- 折扣卷 -->
					<view v-else-if="item.type == 'GIFT'" class="flex-ali flex-direction">
						<h2>{{item.price}}</h2>
						<text class="mj">满{{item.fullPrice}}减{{item.price}}</text>
					</view>
					<!-- 代金券 -->
					<view v-else-if="item.type == 'CASH'" class="flex-ali flex-direction">
						<h2>{{item.price}}</h2>
						<text class="mj">全场通用</text>
					</view>
				</view>
			</view>
			<view class="store-bottom">
				<h3 v-if="item.type == 'DISCOUNT'">新人礼（限兑1次）</h3>
				<h3 v-else>{{item.price}}元优惠劵</h3>
				<text>{{item.points}}积分</text>
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
			}
		}
	}
</script>

<style lang="scss" scoped>
	.store {
		.store-block {
			width: 49%;
			margin-bottom: 20rpx;
		}
		.store-item {
			height: 190rpx;
			background-color: white;
			border-radius: 11rpx;
			position: relative;
			.count {
				position: absolute;
				top: 13rpx;
				right: 13rpx;
				width: 43rpx;
				height: 27rpx;
				background-color: #FFEEE0;
				font-size: 19rpx;
				text-align: center;
				line-height: 27rpx;
				color: #FE6217;
				border-radius: 5rpx;
			}
			.yhj-t {
				width: 75rpx;
				height: 100%;
				text {
					display: inline-block;
					width: 30rpx;
					font-size: 24rpx;
					color: #FFFFFF;
					margin-left: 20rpx;
				}
			}
			.store-content {
				flex: 1;
				color: white;
				.xinren {
					font-size: 34rpx;
				}
				h2 {
					font-size: 69rpx;
				}
				.mj {
					font-size: 22rpx;
				}
			}
		}
		.store-bottom {
			margin-top: 19rpx;
			padding-left: 5rpx;
			h3 {
				color: #343434;
				font-size: 27rpx;
				margin-bottom: 17rpx;
				font-weight: 400;
			}
			text {
				color: $color;
				font-size: 23rpx;
			}
		}
	}
</style>
