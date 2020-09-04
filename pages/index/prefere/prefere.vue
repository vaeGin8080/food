<template>
	<view class="flex flex-direction justify-between" :style="{ height: height }">
		<navBar :list="navList" :navList="navList" :tabCurrentIndex="tabCurrentIndex" @tabClick="tabClick"></navBar>
		<swiper class="swiper" :current="tabCurrentIndex" @change="change" :indicator-dots="false">
			<swiper-item v-for="(item,index) in navList" :key="index">
				<scroll-view @scrolltolower="scrolltolower" scroll-y="true" style="height: 100%">
					<view class="pre-wrap w-100 h-100">
						<prefereItem :List="item.orderList" :state="item.state"></prefereItem>
					</view>
				</scroll-view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
import navBar from '@/components/navBar.vue';
import prefereItem from './prefereItem.vue';
import Json from '@/Json';
export default {
	components: { navBar,prefereItem },
	data() {
		return {
			tabCurrentIndex: 0,
			isShow: false,
			hasNext: true,
			page: 1,
			height: '667px',
			navList: [
				{
					state: 0,
					text: '未使用',
					orderList: [],
					loadingType: 'more',
					count: 2,
				},
				{
					state: 1,
					text: '已使用',
					orderList: [],
					loadingType: 'more',
					count: 3,
				},
				{
					state: 2,
					text: '已过期',
					orderList: [],
					loadingType: 'more',
					count: 1,
				}
			],
		};
	},
	onLoad() {
		let sysheight = uni.getSystemInfoSync().windowHeight;
		this.height = `${sysheight}px`;
		this.init();
	},
	computed: {
	},
	methods: {
		async init(source) {
			//这里是将订单挂载到tab列表下
			let index = this.tabCurrentIndex;
			let navItem = this.navList[index];
			let state = navItem.state;
			if(source === 'tabChange' && navItem.loaded === true){
				//tab切换只有第一次需要加载数据
				console.log('tab');
				return;
			}
			if(navItem.loadingType === 'loading'){
				//防止重复加载
				return;
			}
			navItem.loadingType = 'loading';
			setTimeout(()=>{
				let orderList = Json.orderList.filter(item=> item.state == navItem.state)[0].goodsList;
				orderList.forEach((item,index)=>{
					navItem.orderList.push(item);
				})
				//loaded新字段用于表示数据加载完毕，如果为空可以显示空白页
				this.$set(navItem, 'loaded', true);
				//判断是否还有数据， 有改为 more， 没有改为noMore 
				navItem.loadingType = 'more';
			}, 0);
		},
		scrolltolower(e) {
			// this.init()
		},
		tabClick(index) {
			this.tabCurrentIndex = index;
		},
		change(e) {
			this.tabCurrentIndex = e.detail.current
			this.init('tabChange')
		},
		go(item) {
		}
	}
};
</script>

<style lang="scss" scoped>
	.swiper {
		height: calc(100% - 40px);
	}
	.pre-wrap {
		padding: 20rpx 15rpx;
		
	}
</style>
