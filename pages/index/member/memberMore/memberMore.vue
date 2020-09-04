<template>
	<view class="wrap" :style="{ height: height }">
		<view class="flex-ali flex-direction">
			<image :src="statics.$memberMore"></image>
			<text>披星戴月开发中，敬请期待！</text>
		</view>
	</view>
</template>

<script>
import statics from '@/staticBG';
	export default {
		data() {
			return {
				statics,
				height: '667px'
			};
		},
		onLoad() {
			let sysheight = uni.getSystemInfoSync().windowHeight;
			this.height = `${sysheight}px`;
		},
	}
</script>

<style lang="scss" scoped>
.wrap {
	background-color: white;
	color: #666666;
	font-size: 29rpx;
	image {
		width: 356rpx;
		height: 356rpx;
		margin-top: 134rpx;
		margin-bottom: 54rpx;
	}
}
</style>
