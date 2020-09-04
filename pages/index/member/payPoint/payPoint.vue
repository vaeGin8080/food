<template>
	<view>
		<view class="point-head flex align-start justify-between">
			<view class="flex align-end">
				<h2>1024</h2>
				<text>积分</text>
			</view>
			<image src="../../../../static/img/point.png"></image>
		</view>
		<view class="point-wrap">
			<view class="point-content">
				<view class="point-editor">
					<view class="member-item jf-wrap">
						<view class="flex align-center justify-between"><h2>赚积分</h2></view>
						<view class="jf-item flex align-center justify-between">
							<view class="jf-title flex align-center">
								<image src="@/static/img/member-qd.png"></image>
								<view class="jf-t">
									<text>每日签到(0/7)</text>
									<view class="jf-r">
										<text>连续7日签到</text>
										<text class="jf-act">+60积分</text>
									</view>
								</view>
							</view>
							<text class="jf-btn">去签到</text>
						</view>
						<view class="jf-item flex align-center justify-between">
							<view class="jf-title flex align-center">
								<image src="@/static/img/member-xf.png"></image>
								<view class="jf-t">
									<text>首次消费</text>
									<view class="jf-r">
										<text>首次下单或微信支付</text>
										<text class="jf-act">+50积分</text>
									</view>
								</view>
							</view>
							<text class="jf-btn">去下单</text>
						</view>
						<view class="jf-item flex align-center justify-between">
							<view class="jf-title flex align-center">
								<image src="@/static/img/member-xx.png"></image>
								<view class="jf-t">
									<text>完善信息</text>
									<view class="jf-r">
										<text>完善个人信息</text>
										<text class="jf-act">+50积分</text>
									</view>
								</view>
							</view>
							<text class="jf-btn">去完善</text>
						</view>
						<view class="jf-item flex align-center justify-between">
							<view class="jf-title flex align-center">
								<image src="@/static/img/member-cz.png"></image>
								<view class="jf-t">
									<text>首次充值</text>
									<view class="jf-r">
										<text>首次充值200元或以上</text>
										<text class="jf-act">+300积分</text>
									</view>
								</view>
							</view>
							<text class="jf-btn">去充值</text>
						</view>
						<view class="jf-item flex align-center justify-between">
							<view class="jf-title flex align-center">
								<image src="@/static/img/member-xf.png"></image>
								<view class="jf-t">
									<text>每月消费( (0/4)</text>
									<view class="jf-r">
										<text>一个月内累计消费4次</text>
										<text class="jf-act">+500积分</text>
									</view>
								</view>
							</view>
							<text class="jf-btn">去下单</text>
						</view>
						<view class="jf-item flex align-center justify-between">
							<view class="jf-title flex align-center">
								<image src="@/static/img/member-xf.png"></image>
								<view class="jf-t">
									<text>会员升级</text>
									<view class="jf-r">
										<text>会员升级奖励</text>
										<text class="jf-act">+500积分</text>
									</view>
								</view>
							</view>
							<text class="jf-btn">去升级</text>
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	}
};
</script>

<style lang="scss" scoped>
.point-head {
	height: 225rpx;
	padding: 30rpx 25rpx 0;
	background-color: #fe474f;
	color: white;
	h2 {
		font-size: 50rpx;
		margin-right: 5rpx;
	}
	text {
		display: inline-block;
		margin-bottom: 5rpx;
	}
	image {
		width: 90rpx;
		height: 92rpx;
	}
}
.point-wrap {
	position: relative;
	width: 100%;
	.point-content {
		position: absolute;
		top: -80rpx;
		left: 0;
		width: 100%;
		padding: 0 25rpx;
		.point-editor {
			width: 100%;
			background-color: white;
			padding: 35rpx 25rpx 0;
			box-shadow: 0px 0px 15px 4px rgba(222, 225, 247, 0.3);
			border-radius: 11rpx;
			h2 {
				font-size: 29rpx;
				color: #333333;
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
		}
	}
}
</style>
