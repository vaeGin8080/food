<template>
	<view>
		<u-cell-group>
			<view v-for="(item, index) in list" :key="index">
				<u-cell-item :title="item.label" :label="item.time" :arrow="false">
					<view slot="right-icon">
						<view class="moon flex align-center" :class="{zmoon:item.moon}">
							<text v-if="item.moon">+</text>
							<text v-else>-</text>
							<text>{{ item.money.toFixed(2) }}</text>
						</view>
					</view>
				</u-cell-item>
			</view>
		</u-cell-group>
	</view>
</template>

<script>
export default {
	data() {
		return {
			list: [
				{ label: '线下消费', time: '2020.4.12 09.15.48', moon: true, money: 56.0 },
				{ label: '退款', time: '2020.4.12 09.15.48', moon: false, money: 156.0 },
				{ label: '查额退款', time: '2020.4.12 09.15.48', moon: false, money: 56.0 },
				{ label: '充值赠送', time: '2020.4.12 09.15.48', moon: false, money: 56.0 }
			]
		};
	}
};
</script>

<style lang="scss" scoped>
	.zmoon {
		text {
			color: $color;
		}
	}
	.moon {
		font-size: 33rpx;
		color: #333333;
	}
</style>
