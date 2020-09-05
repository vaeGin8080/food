<template>
	<view class="store flex flex-wrap justify-between">
		<view class="store-block" v-for="(item,index) in List" :key="index">
			<view class="store-item flex" :style="{ background: `url(${bg}) no-repeat center`, backgroundSize: 'cover' }">
				<view class="count">
					VIP{{item.grade}}
				</view>
				<view class="yhj-t flex align-center justify-center">
					<text>优惠劵</text>
				</view>
				<view class="store-content flex-ali flex-direction">
					<!-- 代金券 -->
					<view  class="flex-ali flex-direction">
						<h2>{{item.price}}</h2>
						<text class="mj">全场通用</text>
					</view>
				</view>
			</view>
			<view class="store-bottom">
				<h3>{{item.price}}元优惠劵 (当月有效)</h3>
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
				bg: require('@/static/img/gua1.png')
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
				top: 0;
				right: 0;
				width: 77rpx;
				height: 38rpx;
				background-color: #313131;
				box-shadow: 1px 6rpx 14rpx 0px rgba(215, 183, 207, 0.35);
				border-radius: 0px 6rpx 0px 6rpx;
				font-size: 19rpx;
				text-align: center;
				line-height: 38rpx;
				color: #FFFFFF;
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
