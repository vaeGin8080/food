<template>
	<view class="wrap">
		<memberRecordItem :List="recordList"></memberRecordItem>
	</view>
</template>

<script>
import Json from '@/Json.js';
import memberRecordItem from './memberRecordItem.vue';
	export default {
		components: {memberRecordItem},
		data() {
			return {
				recordList: Json.jfList
			};
		}
	}
</script>

<style lang="scss" scoped>
.wrap {
	padding: 20rpx 25rpx;
}
</style>
