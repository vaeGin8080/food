<template>
	<view>
		<view class="shop-item flex flex-direction" v-for="(item, index) in List" :key="index">
			<view class="item-top flex w-100">
				<view class="store-item flex" :style="{ background: `url(${swit(item.type)}) no-repeat center`, backgroundSize: 'cover' }">
					<view v-if="item.count" class="count">{{ item.count }}张</view>
					<view class="yhj-t flex align-center justify-center"><text>{{item.type | type}}</text></view>
					<view class="store-content flex-ali flex-direction">
						<!-- 新人卷 -->
						<view v-if="item.type == 1" class="gua1">
							<text>￥</text>
							<text>{{ item.price }}</text>
						</view>
						<!-- 折扣卷 -->
						<view v-else-if="item.type == 2" class="gua2 flex-ali flex-direction">
							<h2>{{ item.price }}</h2>
						</view>
						<!-- 代金券 -->
						<view v-else-if="item.type == 3" class="gua3 flex-ali flex-direction"></view>
					</view>
				</view>
				<view class="shop-content flex flex-direction">
					<h3 class="title">{{item.title}}</h3>
					<text class="type">{{item.desc}}</text>
					<view v-if="item.type !== 3" class="flex align-center justify-between">
						<text class="time">
							{{item.time}}
						</text>
					</view>
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
			bgred: require('@/static/img/gua1.png'),
			bgyellow: require('@/static/img/gua2.png'),
			bgpurple: require('@/static/img/gua3.png'),
		};
	},
	filters: {
		type(value) {
			if(value == 1) return '优惠劵';
			else if(value == 2) return '积分';
			else return '礼品';
		}
	},
	methods: {
		swit(value) {
			if(value == 1) return this.bgred;
			else if(value == 2) return this.bgyellow;
			else return this.bgpurple;
		}
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
		width: 239rpx;
		height: 144rpx;
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
			position: relative;
			.gua1 {
				font-size: 23rpx;
				text {
					display: inline-block;
					&:first-child {
						position: absolute;
						left: 30rpx;
						top: 20rpx;
						font-size: 33rpx;
					}
					&:last-child {
						font-size: 59rpx;
					}
				}
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
		padding: 5rpx 16rpx;
		.title {
			color: #1f2f45;
			font-size: 33rpx;
			font-weight: 400;
			@include text-overflow();
		}
		.type {
			display: inline-block;
			margin: 13rpx 0 16rpx;
			color: #666666;
			font-size: 22rpx;
			@include text-overflow();
		}
		.time {
			color: #999999;
			font-size: 22rpx;
		}
	}
}
</style>
