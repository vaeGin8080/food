<template>
	<scroll-view class="store" scroll-x>
		<view class="store-block" v-for="(item, index) in List" :key="index">
			<view class="store-item"><image mode="aspectFill" :src="item.url"></image></view>
			<view class="store-bottom flex flex-direction">
				<h3>{{ item.title }}</h3>
				<view v-if="VIP" class="cz">成长值+100</view>
				<text>{{ item.price }}积分</text>
			</view>
		</view>
	</scroll-view>
</template>

<script>
export default {
	props: {
		List: {
			type: Array,
			default() {
				return [];
			}
		},
		VIP: {
			type: Boolean,
			default: false
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
.store {
	white-space: nowrap;
	.store-block {
		width: 279rpx;
		display: inline-block;
		margin-right: 20rpx;
		border-radius: 12px 12px 0px 0px;
	}
	.store-item {
		position: relative;
		image {
			width: 100%;
			height: 274rpx;
			border-radius: 12px 12px 0px 0px;
		}
	}
	.store-bottom {
		background-color: white;
		padding: 20rpx;
		h3 {
			color: #343434;
			font-size: 26rpx;
			margin-bottom: 14rpx;
			font-weight: 400;
		}
		text {
			color: $color;
			font-size: 23rpx;
		}
		.cz {
			display: inline-block;
			width: 156rpx;
			height: 33rpx;
			background: #F6D1B5;
			border-radius: 17rpx;
			margin-bottom: 14rpx;
			font-size: 22rpx;
			color: #964B12;
			text-align: center;
			line-height: 33rpx;
		}
			
	}
}
</style>
