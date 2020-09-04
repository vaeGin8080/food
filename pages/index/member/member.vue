<template>
	<view class="wrap">
		<view class="banner" :style="{ background: `url(${statics.$memberCenter})`, backgroundSize: 'cover' }">
			<u-navbar back-text="会员中心" back-icon-color="#fff" :background="{ background: '', border: 'none' }" :back-text-style="{ color: '#fff' }"></u-navbar>
			<view class="banner-content">
				<view class="banner-user flex align-center">
					<image mode="aspectFill" src="https://vaegin.top/img/mm.jpg"></image>
					<text class="user-name">优异</text>
					<text class="user-dj">VIP1</text>
				</view>
				<view class="member-cj flex align-center justify-between">
					<view class="member-cz flex flex-direction align-center">
						<text>341</text>
						<text>我的成长值</text>
					</view>
					<view class="member-sj flex-ali">
						<text>
							还差
							<text style="color: #FBE685;">78</text>
							成长值升级为VIP2
						</text>
						<u-icon name="arrow-right" color="#fff" size="22"></u-icon>
					</view>
				</view>
				<view></view>
				<view class="member-hy">
					<view class="hy flex align-center justify-between">
						<text>VIP会员，每月均可领取优惠券</text>
						<text class="lq">立即领取</text>
					</view>
				</view>
			</view>
		</view>
		<view class="member-content">
			<view class="member-item">
				<h2>会员特权</h2>
				<view>
					<u-row>
						<u-col span="3" v-for="(item, index) in navList" :key="index" @click="go(item.url)">
							<view class="nav-item flex flex-direction justify-center align-center">
								<image :src="item.src"></image>
								<text>{{ item.label }}</text>
							</view>
						</u-col>
					</u-row>
				</view>
			</view>
			<view class="member-item jf-wrap">
				<view class="flex align-center justify-between">
					<h2>赚积分</h2>
					<view @click="pointMore">
						<text class="right-t">全部</text>
						<u-icon name="arrow-right" color="#666666" size="22"></u-icon>
					</view>
				</view>
				<view class="jf-item flex align-center justify-between u-border-bottom">
					<view class="jf-title flex align-center">
						<image src="../../../static/img/member-qd.png"></image>
						<text>每日签到(0/7)</text>
					</view>
					<text class="jf-btn">去签到</text>
				</view>
				<view class="jf-item flex align-center justify-between">
					<view class="jf-title flex align-center">
						<image src="../../../static/img/member-xf.png"></image>
						<text>首次消费</text>
					</view>
					<text class="jf-btn">去下单</text>
				</view>
			</view>
			<view class="friend" :style="{ background: `url(${statics.$memberFriend})`, backgroundSize: 'cover' }" @click="goFriend"></view>
			<view class="member-item">
				<view class="flex align-center justify-between">
					<h2>积分兑换</h2>
					<view>
						<text class="right-t">积分商城</text>
						<u-icon name="arrow-right" color="#666666" size="22"></u-icon>
					</view>
				</view>
				<view class="jf-change flex align-center justify-around">
					<view class="change-left">
						<view class="change-h2">
							<h3>兑好劵</h3>
							<text>首次领15元红包</text>
						</view>
					</view>
					<view class="flex-sub h-100 flex flex-direction justify-between">
						<view class="change-t flex align-center"><text>精美礼品限量兑</text></view>
						<view class="change-b flex align-center"><text>超值礼包月月领</text></view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import statics from '@/staticBG';
export default {
	data() {
		return {
			statics,
			navList: [
				{ label: '生日惊喜', src: '../../../static/img/member-nav1.png',url: '/pages/index/member/memberBirthday/memberBirthday'},
				{ label: '会员日', src: '../../../static/img/member-nav2.png',url: '/pages/index/member/memberDay/memberDay'},
				{ label: '升级礼', src: '../../../static/img/member-nav3.png',url: '/pages/index/member/memberGift/memberGift'},
				{ label: '更多特权', src: '../../../static/img/member-nav4.png',url: '/pages/index/member/memberMore/memberMore'}
			]
		};
	},
	methods: {
		go(url) {
			if(!url) return;
			uni.navigateTo({
				url: url
			})
		},
		pointMore() {
			uni.navigateTo({
				url: '/pages/index/member/payPoint/payPoint'
			})
		},
		goFriend() {
			uni.navigateTo({
				url: '/pages/index/member/inviteFriend/inviteFriend'
			})
		}
	}
};
</script>

<style lang="scss" scoped>
.banner {
	width: 100%;
	height: 520rpx;
	padding: 30rpx 0 0 25rpx;
	background-size: cover;
	position: relative;
}
.banner-user {
	color: #ffffff;
	image {
		width: 83rpx;
		height: 83rpx;
		border-radius: 50%;
	}
	.user-name {
		display: inline-block;
		font-size: 26rpx;
		margin: 0 15rpx;
	}
	.user-dj {
		display: inline-block;
		padding: 8rpx 18rpx;
		font-size: 22rpx;
		background-color: #fdb02b;
		border-radius: 17rpx;
	}
}
.member-cj {
	margin-top: 20rpx;
	.member-cz {
		color: white;
		padding-left: 20rpx;
		text {
			&:first-child {
				display: inline-block;
				font-size: 33rpx;
				margin-bottom: 10rpx;
			}
			&:last-child {
				font-size: 22rpx;
			}
		}
	}
	.member-sj {
		width: 328rpx;
		height: 45rpx;
		color: white;
		font-size: 22rpx;
		background: rgba(0, 0, 0, 0.2);
		border-radius: 20rpx 0px 0px 20rpx;
	}
}
.member-hy {
	position: absolute;
	left: 0;
	bottom: 0;
	width: 100%;
	height: 80rpx;
	padding: 0 40rpx;
	.hy {
		height: 100%;
		background: #3b3a3a url(@/static/img/huangguan.png) no-repeat left;
		background-size: contain;
		padding: 0 30rpx;
		border-radius: 11rpx 11rpx 0px 0px;
		color: #fbe685;
		font-size: 26rpx;
	}
	.lq {
		display: inline-block;
		width: 130rpx;
		height: 33rpx;
		background: #fbe685;
		border-radius: 17rpx;
		line-height: 33rpx;
		font-size: 22rpx;
		color: #3b3a3a;
		text-align: center;
	}
}

.member-content {
	padding: 20rpx 25rpx;
	.member-item {
		background-color: white;
		padding: 20rpx;
		border-radius: 11rpx;
		margin-bottom: 18rpx;
		h2 {
			color: #333333;
			font-size: 29rpx;
		}
		.right-t {
			font-size: 23rpx;
			color: #666666;
		}
		.nav-item {
			margin-top: 25rpx;
			image {
				width: 84rpx;
				height: 84rpx;
				margin-bottom: 16rpx;
			}
			text {
				color: #333333;
				font-size: 22rpx;
			}
		}
		.jf-item {
			padding: 20rpx 0;
			.jf-title {
				color: #333333;
				font-size: 26rpx;
				font-weight: 500;
				image {
					width: 64rpx;
					height: 64rpx;
					margin-right: 14rpx;
				}
			}
			.jf-btn {
				display: inline-block;
				width: 109rpx;
				height: 40rpx;
				background: #fe474f;
				border-radius: 19px;
				text-align: center;
				font-size: 22rpx;
				color: white;
				line-height: 40rpx;
			}
		}
		.jf-change {
			height: 192rpx;
			margin-top: 25rpx;
			.change-left {
				width: calc(50% - 10rpx);
				height: 100%;
				background: url(../../../static/img/jf-change1.png) no-repeat;
				background-size: cover;
				margin-right: 10rpx;
				.change-h2 {
					margin-top: 42rpx;
					margin-left: 20rpx;
					h3 {
						color: #d81921;
						font-size: 33rpx;
						margin-bottom: 14rpx;
						font-weight: bold;
					}
					text {
						color: #d71821;
						font-size: 22rpx;
					}
				}
			}
			.change-t {
				width: 100%;
				height: 49%;
				background: url(../../../static/img/jf-change2.png) no-repeat;
				background-size: cover;
				padding-left: 22rpx;
				color: #1080b4;
				font-size: 22rpx;
				font-weight: bold;
			}
			.change-b {
				width: 100%;
				height: 49%;
				background: url(../../../static/img/jf-change3.png) no-repeat;
				background-size: cover;
				padding-left: 22rpx;
				color: #ee6b23;
				font-size: 22rpx;
				font-weight: bold;
			}
		}
	}
	.jf-wrap {
		padding-bottom: 0;
	}
}
.friend {
	height: 120rpx;
	margin-bottom: 20rpx;
}
</style>
