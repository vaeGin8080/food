<template>
	<view class="wrap">
		<u-swiper :list="list" height="528" :interval="5000"></u-swiper>
		<view class="nav-wrap">
			<view class="nav">
				<view class="nav-content flex justify-around">
					<view class="nav-item flex flex-direction align-center" v-for="(item, index) in navList" :key="index">
						<image :src="item.src"></image>
						<text>{{ item.label }}</text>
					</view>
				</view>
			</view>
		</view>
		<view class="title"><h3>会员秒杀</h3></view>
		<view class="product">
			<swiperItem :List="swiperList"></swiperItem>
		</view>
		<view class="title flex align-center justify-between"><h3>热销产品</h3><image src="../../static/img/right-jt.png"></image></view>
		<view class="contain hot">
			<view class="hot-title flex align-center">
				<image src="../../static/img/fire.png"></image>
				<text>今日必推</text>
			</view>
			<shopItem :List="swiperList"></shopItem>
		</view>
		<view class="title flex align-center justify-between"><h3>为您推荐</h3><image src="../../static/img/right-jt.png"></image></view>
		<view class="contain recommend">
			<view class="recommend-nav flex justify-around align-center">
				<view class="flex-sub flex align-center justify-center" v-for="(item,index) in recommendList" :key="index">
					<text>{{item.label}}</text>
					<image src="../../static/img/jiantou.png"></image>
				</view>
			</view>
			<recommendItem :List="swiperList"></recommendItem>
		</view>
	</view>
</template>

<script>
import swiperItem from './swiperItem.vue';
import shopItem from './shopItem.vue';
import recommendItem from './recommendItem.vue';
export default {
	components: {swiperItem,shopItem,recommendItem},
	data() {
		return {
			recommendList: [
				{label: '星级',id:1},
				{label: '价格',id:2},
				{label: '折扣',id:3},
				{label: '时间',id:4},
			],
			list: [
				{
					image: 'https://cdn.uviewui.com/uview/swiper/1.jpg',
					title: '昨夜星辰昨夜风，画楼西畔桂堂东'
				},
				{
					image: 'https://cdn.uviewui.com/uview/swiper/2.jpg',
					title: '身无彩凤双飞翼，心有灵犀一点通'
				},
				{
					image: 'https://cdn.uviewui.com/uview/swiper/3.jpg',
					title: '谁念西风独自凉，萧萧黄叶闭疏窗，沉思往事立残阳'
				}
			],
			navList: [
				{
					label: '买单',
					src: '/static/img/nav1.png'
				},
				{
					label: '优惠券',
					src: '/static/img/nav2.png'
				},
				{
					label: '钱包',
					src: '/static/img/nav3.png'
				},
				{
					label: '会员中心',
					src: '/static/img/nav4.png'
				},
				{
					label: '积分商城',
					src: '/static/img/nav5.png'
				}
			],
			swiperList: [
				{
					id: 0,
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg',
					price: 999,
					orignPrice: 1699,
					title: '阳澄湖大闸蟹',
					people: 2456,
					type: '提拉米苏、水果拼盘、零食小吃、饮料、零食小吃、饮料',
					zhe: 7.66
				},
				{
					id: 1,
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big37006.jpg',
					price: 169,
					orignPrice: 888,
					title: '炸鸡可乐',
					people: 2456,
					type: '提拉米苏、水果拼盘、零食小吃、饮料',
					zhe: 7.66
				},
				{
					id: 2,
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big39000.jpg',
					price: 474,
					orignPrice: 666,
					title: '寿司',
					people: 2456,
					type: '提拉米苏、水果拼盘、零食小吃、饮料',
					zhe: 7.66
				},
				{
					id: 3,
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big10001.jpg',
					price: 66,
					orignPrice: 88,
					title: '叉烧包',
					people: 2456,
					type: '提拉米苏、水果拼盘、零食小吃、饮料',
					zhe: 7.66
				},
			]
		};
	},
	onLoad() {},
	methods: {}
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
	&>image {
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
		background-color: #FE474F;
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

</style>
