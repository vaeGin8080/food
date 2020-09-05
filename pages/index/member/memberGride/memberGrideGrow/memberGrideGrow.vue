<template>
	<view>
		<recordList :List="list"></recordList>
	</view>
</template>

<script>
import recordList from '@/components/recordList/recordList.vue'
export default {
	components: {recordList},
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
