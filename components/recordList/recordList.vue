<template>
	<u-cell-group>
		<view v-for="(item, index) in List" :key="index">
			<u-cell-item :title="item.label" :label="item.time" :arrow="false">
				<view slot="right-icon">
					<view class="moon flex align-center" :class="{ zmoon: item.moon }">
						<text v-if="item.moon">+</text>
						<text v-else>-</text>
						<text>{{ item.money.toFixed(2) }}</text>
					</view>
				</view>
			</u-cell-item>
		</view>
	</u-cell-group>
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
		breed: {
			type: String,
			default: ''
		}
	},
	data() {
		return {};
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
