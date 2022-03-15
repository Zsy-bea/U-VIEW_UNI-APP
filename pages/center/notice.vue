<template>
	<view class="page-wrapper">
		<view class="tab-wrapper">
			<view v-for="item in tablist" class="tab-item" :class="activeName==item?'tab-item-active':'tab-item-narmal'" @click="activeItem(item)">
				<view class="text-box">
					{{item}}
				</view>
			</view>
		</view>
		<view class="scroll-view-wrapper">
			<scroll-view v-if="activeName=='通知'" scroll-y="true" refresher-enabled refresher-background="#F4F5F7" :refresher-threshold="100"></scroll-view>
			<scroll-view scroll-y="true" v-if="activeName=='公告'" refresher-enabled refresher-background="#F4F5F7" :refresher-threshold="100"></scroll-view>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				tablist: ['通知', '公告'],
				activeName: '通知'
			}
		},
		methods: {
			activeItem(item) {
				this.activeName = item;
			}
		}
	}
</script>

<style scoped lang="scss">
	.page-wrapper {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		.scroll-view-wrapper {
			padding: 32rpx 0;
			flex: 1;
			overflow: hidden;
			scroll-view {
				height: 100%;
			}
		}
		.tab-wrapper {
			width: 100%;
			background: #fff;
			display: flex;
			align-items: center;
			z-index: 100;
			.tab-item {
				text-align: center;
				flex: 1;
				display: flex;
				justify-content: center;
				align-items: center;
				.text-box {
					width: 152rpx;
					font-size: 16px;
					line-height: 84rpx;
					height: 84rpx;
				}
			}
			.tab-item-active {
				.text-box {
					border-bottom: 2px solid #5476FD;
					color: #5476FD;
				}
			}
		}
	}
</style>
