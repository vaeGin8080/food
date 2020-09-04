<template>
	<view class="wrap" :style="{ height: height }">
		<view class="banner" :style="{background: `url(${statics.$wallet})`,backgroundSize: 'cover'}">
			<u-navbar back-text="钱包" back-icon-color="#fff" :background="{ background: '', border: 'none' }" :back-text-style="{ color: '#fff' }"></u-navbar>
			<view class="mx flex align-center justify-end"  @click="go">
				<text>交易明细</text>
				<image src="@/static/img/right-jt-white.png"></image>
			</view>
			<view class="ye flex flex-direction justify-center align-center">
				<h2>123.00元</h2>
				<text>余额</text>
			</view>
		</view>
		<view class="wallet-content">
			<view class="flex flex-wrap justify-between">
				<view
					:class="{ active: active == index }"
					class="wallet-item flex flex-direction justify-center align-center"
					v-for="(item, index) in payList"
					:key="index"
					@click="choose(item, index)"
				>
					<h3>{{ item.price }}元</h3>
					<text>送{{ item.givePrice }}元</text>
				</view>
				<view class="wallet-item flex flex-direction justify-center align-center"><h3>其他金额</h3></view>
			</view>
			<view class="btn">
				<u-button type="error" @click="recharge">
					<view class="flex-ali" v-if="activePrice && activePrice.price">
						<text>￥</text>
						<h3>{{ activePrice.price }}</h3>
					</view>
					<text>立即充值</text>
				</u-button>
			</view>
			<view class="speak">
				<text>说明</text>
				<view class="s-p" v-for="(item,index) in speak" :key="index">
					{{index+1}} <text>、</text> {{item}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import Json from '@/Json.js';
import statics from '@/staticBG';
export default {
	data() {
		return {
			statics,
			height: '667px',
			active: -1,
			activePrice: {},
			payList: Json.payList,
			speak: ['一次性充值500可升级为VIP1红卡会员','一次性充值1000可升级为VIP2银卡会员'],
		};
	},
	onLoad() {
		let sysheight = uni.getSystemInfoSync().windowHeight;
		this.height = `${sysheight}px`;
	},
	methods: {
		choose(item, index) {
			this.active = index;
			this.activePrice = item;
		},
		go() {
			console.log(1);
			uni.navigateTo({
				url: '/pages/index/wallet/walletDetail/walletDetail'
			})
		},
		recharge() {
			if(!this.activePrice || !this.activePrice.price) return;
			uni.showToast({
				title:'充值成功'
			})
			this.activePrice = {};
			this.active = -1;
		}
	}
};
</script>

<style lang="scss" scoped>
.wrap {
	height: 100%;
	background-color: white;
}
.banner {
	width: 100%;
	height: 440rpx;
	padding: 30rpx 20rpx;
	.mx {
		text {
			color: #ffffff;
			font-size: 22rpx;
		}
		image {
			width: 16rpx;
			height: 16rpx;
			margin-left: 10rpx;
		}
	}
	.ye {
		margin-top: 20rpx;
		color: #ffffff;
		h2 {
			font-size: 83rpx;
			margin-bottom: 10rpx;
		}
		text {
			font-size: 22rpx;
		}
	}
}

.wallet-content {
	padding: 36rpx 25rpx;
}
.wallet-item {
	width: 220rpx;
	height: 152rpx;
	background: #ffffff;
	border: 1rpx solid #656565;
	border-radius: 11rpx;
	margin-bottom: 20rpx;
	h3 {
		margin-bottom: 10rpx;
		color: #000000;
	}
	text {
		color: #999999;
		font-size: 22rpx;
	}
}
.active {
	border-color: $color;
	h3,
	text {
		color: $color !important;
	}
}
.btn {
	margin-top: 60rpx;
	font-size: 33rpx;
	h3 {
		margin-right: 10rpx;
		font-size: 40rpx;
	}
}
.speak {
	margin-top: 94rpx;
	font-size: 22rpx;
	color: #999999;
	text {
		display: inline-block;
		margin-bottom: 10rpx;
	}
	.s-p {
		margin: 5rpx 0;
	}
}
</style>
