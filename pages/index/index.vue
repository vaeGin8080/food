<template>
	<view class="wrap">
		<u-swiper :list="list" height="528" :interval="5000"></u-swiper>
		<view class="nav-wrap">
			<view class="nav">
				<view class="nav-content flex justify-around">
					<view class="nav-item flex flex-direction align-center" v-for="(item, index) in navList" :key="index" @click="jump(item.url)">
						<image :src="item.src"></image>
						<text>{{ item.label }}</text>
					</view>
				</view>
			</view>
		</view>
		<view class="title"><h3>会员秒杀</h3></view>
		<view class="product"><swiperItem :List="swiperList"></swiperItem></view>
		<view class="title flex align-center justify-between">
			<h3>热销产品</h3>
			<!-- <image src="../../static/img/right-jt.png"></image> -->
			<u-icon name="arrow-right" color="#25344A" size="22"></u-icon>
		</view>
		<view class="contain hot">
			<view class="hot-title flex align-center">
				<image src="../../static/img/fire.png"></image>
				<text>今日必推</text>
			</view>
			<shopItem :List="swiperList"></shopItem>
		</view>
		<view class="title flex align-center justify-between">
			<h3>为您推荐</h3>
			<u-icon name="arrow-right" color="#25344A" size="22"></u-icon>
			<!-- <image src="../../static/img/right-jt.png"></image> -->
		</view>
		<view class="contain recommend">
			<view class="recommend-nav flex justify-around align-center">
				<view class="flex-sub flex align-center justify-center" v-for="(item, index) in recommendList" :key="index">
					<text>{{ item.label }}</text>
					<u-icon name="arrow-down" color="#25344A" size="22"></u-icon>
					<!-- <image src="../../static/img/jiantou.png"></image>	 -->
				</view>
			</view>
			<recommendItem :List="goodsList"></recommendItem>
			<u-loadmore :status="status" bg-color="#f1f1f1"/>
		</view>
		<u-popup v-model="show" mode="center" :zoom="false" :mask-close-able="false">
			<view class="member">
				<view class="member-bg" :style="{background: `transparent url(${statics.$memberCard}) no-repeat bottom`,backgroundSize: 'cover'}">
					<text class="lq">立刻领取</text>
				</view>
				<image class="close" src="../../static/img/close.png" @click="show = false"></image>
			</view>
		</u-popup>
	</view>
</template>

<script>
import swiperItem from './swiperItem.vue';
import shopItem from './shopItem.vue';
import recommendItem from './recommendItem.vue';
import Json from '@/Json.js';
import statics from '@/staticBG';
export default {
	components: { swiperItem, shopItem, recommendItem },
	data() {
		return {
			statics,
			show: false,
			status: 'loadmore',
			recommendList: [{ label: '星级', id: 1 }, { label: '价格', id: 2 }, { label: '折扣', id: 3 }, { label: '时间', id: 4 }],
			list: Json.bannerlList,
			navList: [
				{
					label: '买单',
					src: '/static/img/nav1.png',
					url: '/pages/index/pay/pay'
				},
				{
					label: '优惠券',
					src: '/static/img/nav2.png',
					url: '/pages/index/prefere/prefere'
				},
				{
					label: '钱包',
					src: '/static/img/nav3.png',
					url: '/pages/index/wallet/wallet'
				},
				{
					label: '会员中心',
					src: '/static/img/nav4.png',
					url: '/pages/index/member/member'
				},
				{
					label: '积分商城',
					src: '/static/img/nav5.png',
					url: '/pages/index/memberStore/memberStore'
				}
			],
			swiperList: Json.swiperList,
			goodsList: Json.swiperList,
		};
	},
	onLoad() {},
	onReachBottom() {
		this.init()
	},
	methods: {
		init() {
			setTimeout(()=>{
				this.goodsList = this.goodsList.concat(Json.swiperList)
				this.status = 'loading'
			},500)
		},
		jump(url) {
			if(url) {
				uni.navigateTo({
					url: url
				})
			}else {
				return;
			}
		}
	}
};
</script>

<style lang="scss" scoped>
.content {
	background-color: #f5f5f5;
}
.nav-wrap {
	position: relative;
	height: 70rpx;
	.nav {
		position: absolute;
		top: -110rpx;
		left: 0;
		width: 100%;
		height: 180rpx;
		padding: 0 25rpx;
	}
	.nav-content {
		width: calc(100% - 50rpx);
		height: 180rpx;
		background-color: white;
		padding: 35rpx 25rpx;
		box-shadow: 0px 0px 15px 4px rgba(222, 225, 247, 0.3);
		border-radius: 11rpx;
		position: absolute;
		.nav-item {
			image {
				width: 64rpx;
				height: 64rpx;
				margin-bottom: 21rpx;
			}
			text {
				font-size: 22rpx;
				font-weight: 400;
				color: #1f2f45;
			}
		}
	}
}

.title {
	margin: 20rpx 0;
	padding: 0 25rpx;
	& > h3 {
		font-size: 29rpx;
		font-weight: bold;
		color: #333333;
	}
	& > image {
		width: 24rpx;
		height: 24rpx;
	}
}

.product {
	margin-top: -50rpx;
}
.contain {
	padding: 0 25rpx;
}
.hot {
	.hot-title {
		height: 50rpx;
		padding: 0 15rpx;
		background-color: #fe474f;
		border-top-left-radius: 11rpx;
		border-top-right-radius: 11rpx;
		color: white;
		font-size: 30rpx;
		image {
			width: 30rpx;
			height: 30rpx;
			margin-right: 10rpx;
		}
	}
}
.recommend {
	.recommend-nav {
		height: 80rpx;
		color: #666666;
		font-size: 26rpx;
		image {
			width: 18rpx;
			height: 18rpx;
			margin-left: 5rpx;
		}
	}
}

.member {
	position: relative;
	height: 650rpx;
	.member-bg {
		width: 750rpx;
		height: 564rpx;
		position: relative;
		.lq {
			position: absolute;
			left: 50%;
			bottom: 80rpx;
			transform: translateX(-50%);
			display: inline-block;
			width: 263rpx;
			height: 61rpx;
			border: 1px solid #ffff00;
			border-radius: 5px;
			color: #fadb33;
			font-size: 33rpx;
			text-align: center;
			line-height: 61rpx;
		}
	}
	.close {
		position: absolute;
		left: 50%;
		bottom: 0rpx;
		transform: translateX(-50%);
		width: 46rpx;
		height: 46rpx;
	}
}
.u-mode-center-box {
	background-color: transparent;
}
</style>
