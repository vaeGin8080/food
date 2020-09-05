<template>
	<view class="gridew-wrap">
		<u-navbar back-text="会员等级" back-icon-color="#fff" :background="{ background: '#FE474F', border: 'none' }" :back-text-style="{ color: '#fff' }"></u-navbar>
		<view class="banner-content">
			<view class="banner-h flex align-center justify-between">
				<view class="banner-user flex align-center">
					<image mode="aspectFill" src="https://vaegin.top/img/mm.jpg"></image>
					<text class="user-name">晓风残月</text>
					<text class="user-dj">VIP1</text>
				</view>
				<navigator url="/pages/index/member/memberGride/memberGrideGrow/memberGrideGrow" class="member-cz flex align-center">
					<text>341</text>
					<text>成长值</text>
				</navigator>
			</view>
			<u-row gutter="16" justify="center" class="grade-a">
				<u-col span="3"><view class="a1">VIP1</view></u-col>
				<u-col span="3"><view class="">VIP2</view></u-col>
				<u-col span="3"><view class="">VIP3</view></u-col>
				<u-col span="3"><view class="">VIP4</view></u-col>
			</u-row>
		</view>
		<view class="grade-content">
			<view class="content">
				<view class="grade-rule flex align-center justify-end">
					<text>等级规则</text>
					<u-icon name="question-circle" color="#666666" size="27"></u-icon>
				</view>
				<view class="member-grade flex align-end justify-center">
					<view class="left"></view>
					<view class="bottom"></view>
					<view class="top"></view>
					<navigator url="/pages/index/member/memberGride/memberGrideGrow/memberGrideGrow" class="cz">成长值</navigator>
					<view class="grade-d grade1">
						<view class="zb">VIP1</view>
						<view class="zhe">
							<text>9.85</text>
							折
						</view>
						<view class="jifen">300</view>
						<view class="current">当前享</view>
					</view>
					<view class="grade-d grade2">
						<view class="zb">VIP2</view>
						<view class="zhe">
							<text>9.70</text>
							折
						</view>
						<view class="jifen">2000</view>
					</view>
					<view class="grade-d grade3">
						<view class="zb">VIP3</view>
						<view class="zhe">
							<text>9.50</text>
							折
						</view>
						<view class="jifen">8000</view>
					</view>
					<view class="grade-d grade4">
						<view class="zb">VIP4</view>
						<view class="zhe">
							<text>9.00</text>
							折
						</view>
						<view class="jifen">15000</view>
					</view>
				</view>
				<view class="liet-wrap">
					<view class="jf-item flex align-center justify-between">
						<view class="jf-title flex align-center">
							<image src="@/static/img/member-xf.png"></image>
							<view class="jf-t">
								<text>折扣优惠</text>
								<view class="jf-r">
									可享受优惠
									<text class="jf-act">9.85折</text>
									优惠
								</view>
							</view>
						</view>
					</view>
					<view class="jf-item flex align-center justify-between">
						<view class="jf-title flex align-center">
							<image src="@/static/img/member-xf.png"></image>
							<view class="jf-t">
								<text>专属优惠劵</text>
								<view class="jf-r">
									每月可领取
									<text class="jf-act">5元</text>
									优惠卷
								</view>
							</view>
						</view>
					</view>
					<view class="jf-item flex align-center justify-between">
						<view class="jf-title flex align-center">
							<image src="@/static/img/member-xf.png"></image>
							<view class="jf-t">
								<text>升级送积分</text>
								<view class="jf-r">
									升级即送
									<text class="jf-act">500</text>
									积分
								</view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="store-item item-two">
			<view class="store-top flex align-center justify-between">
				<h2>VIP升级攻略</h2>
				<navigator url="/pages/index/member/memberGride/memberGrideGift/memberGrideGift">
					<text class="right-t">查看更多</text>
					<u-icon name="arrow-right" color="#666666" size="22"></u-icon>
				</navigator>
			</view>
			<memerStoreExchange :List="exChangeList" :VIP="true"></memerStoreExchange>
		</view>
	</view>
</template>

<script>
import Json from '@/Json.js';
import memerStoreExchange from '../../memberStore/memerStoreExchange.vue';
export default {
	components: { memerStoreExchange },
	data() {
		return {
			exChangeList: Json.swiperList
		};
	}
};
</script>

<style lang="scss" scoped>
.gridew-wrap {
	.banner-content {
		height: 480rpx;
		padding: 20rpx;
		color: white;
		background-color: $color;
	}
	.banner-h {
		margin-bottom: 30rpx;
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
		.member-cz {
			color: white;
			padding-left: 20rpx;
			text {
				&:first-child {
					display: inline-block;
					font-size: 33rpx;
				}
				&:last-child {
					font-size: 22rpx;
				}
			}
		}
	}
	.grade-a {
		view {
			width: 65rpx;
			margin: 0 auto;
			padding: 10rpx 0;
			text-align: center;
		}
		.a1 {
			border-bottom: 1rpx solid white;
		}
	}
}

.grade-content {
	position: relative;
	padding: 20rpx;
	min-height: 450rpx;
	.content {
		position: absolute;
		left: 25rpx;
		top: -270rpx;
		width: calc(100% - 50rpx);
		padding: 20rpx;
		background-color: white;
		border-radius: 11rpx;
		.grade-rule {
			color: #666666;
			font-size: 22rpx;
			margin-bottom: 10rpx;
			text {
				display: inline-block;
				margin-right: 5rpx;
			}
		}
		.member-grade {
			position: relative;
			height: 230rpx;
			.left {
				position: absolute;
				left: 0;
				top: 0;
				width: 12rpx;
				height: 100%;
				background: url(../../../../static/img/grade-left.png) no-repeat;
				background-size: cover;
			}
			.bottom {
				position: absolute;
				left: 0;
				bottom: 0;
				width: 100%;
				height: 12rpx;
				background: url(../../../../static/img/grade-bottom.png) no-repeat;
			}
			.top {
				position: absolute;
				top: 20rpx;
				left: 80rpx;
				width: 475rpx;
				height: 110rpx;
				background: url(../../../../static/img/grade-top.png) no-repeat center;
				background-size: contain;
				transform: skewY(-1deg);
			}
			.cz {
				position: absolute;
				right: 0;
				bottom: -50rpx;
				text-align: center;
				font-size: 22rpx;
				color: #ab4908;
			}
			.grade-d {
				width: 93rpx;
				margin-right: 30rpx;
				position: relative;
				.zb {
					position: absolute;
					bottom: -15rpx;
					left: 0;
					width: 100%;
					height: 33rpx;
					background: #ab4908;
					border-radius: 17rpx;
					font-size: 22rpx;
					color: white;
					text-align: center;
					line-height: 33rpx;
				}
				.zhe {
					position: absolute;
					top: 50rpx;
					left: 0;
					width: 100%;
					text-align: center;
					font-size: 22rpx;
					color: #ab4908;
					text {
						color: $color;
					}
				}
				.jifen {
					position: absolute;
					bottom: -50rpx;
					left: 0;
					width: 100%;
					text-align: center;
					font-size: 22rpx;
					color: #ab4908;
				}
				.current {
					position: absolute;
					top: -30rpx;
					left: 5rpx;
					width: 81rpx;
					height: 34rpx;
					text-align: center;
					font-size: 19rpx;
					color: white;
					line-height: 34rpx;
					background: url(../../../../static/img/grade-current.png);
					background-size: cover;
				}
			}
			.grade1 {
				height: 133rpx;
				background: url(../../../../static/img/grade-vip2.png) no-repeat;
			}
			.grade2 {
				height: 162rpx;
				background: url(../../../../static/img/grade-vip2.png) no-repeat;
			}
			.grade3 {
				height: 189rpx;
				background: url(../../../../static/img/grade-vip3.png) no-repeat;
			}
			.grade4 {
				height: 216rpx;
				background: url(../../../../static/img/grade-vip4.png) no-repeat;
			}
		}
	}
}
.liet-wrap {
	margin-top: 60rpx;
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
		.jf-t {
			display: flex;
			flex-direction: column;
			.jf-r {
				margin-top: 5rpx;
				margin-left: 5rpx;
				color: #999999;
				font-size: 22rpx;
			}
			.jf-act {
				display: inline-block;
				color: $color !important;
				margin-left: 5rpx;
			}
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

.store-item {
	margin: 0 20rpx;
	padding: 24rpx 20rpx;
	margin-bottom: 20rpx;
	border-radius: 12rpx;
	.store-top {
		margin-bottom: 24rpx;
		h2 {
			color: #343434;
			font-size: 29rpx;
		}
		.right-t {
			font-size: 23rpx;
			color: #666666;
		}
	}
}
</style>
