<template>
	<view class="wrap">
		<memberGuatem :List="list"></memberGuatem>
	</view>
</template>

<script>
import Json from '@/Json.js';
import memberGuatem from '../memberGuatem.vue';
	export default {
		components: {memberGuatem},
		data() {
			return {
				list: [
					{
						title: '10元优惠券',
						desc: '满69减10优惠劵',
						type: 1,
						price: 10,
						time: '2020.04.16-2020'
					},
					{
						title: '12积分',
						desc: '1-999区间内随机刮出',
						type: 2,
						price: '1-999',
						time: '2020.04.16-2020'
					},
					{
						title: '精美礼品',
						desc: '具体奖品请以实物为准',
						type: 3,
						time: '2020.04.16-2020'
					}
				]
			};
		}
	}
</script>

<style lang="scss" scoped>
.wrap {
	padding: 20rpx 25rpx;
}
</style>
