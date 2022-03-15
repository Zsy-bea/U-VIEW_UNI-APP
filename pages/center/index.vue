<template>
	<view class="page-wrapper">
		<view class="page-header">
			<image src="../../static/top-bg.png" mode="widthFix"></image>
			<view class="header-content">
				<view class="content-left">
					<image src="../../static/center.png" mode="widthFix"></image>
				</view>
				<view class="content-center">
					<view class="top">
						张三
					</view>
					<view class="bottom">
						xxxxxxxxxxx公司
					</view>
				</view>
			</view>
		</view>
		<view class="operate-list">
			<view class="list-item" v-for="(item,i) in list" @click="toSomePage(item)">
				<view class="item-icon">
					<image :src="item.icon" mode="aspectFit"></image>
				</view>
				<view class="item-content" :class="{ border: i!=0 }">
					<view class="item-content-title">
						{{item.title}}
					</view>
				</view>

			</view>
		</view>
		<view class="button-wrapper">
			<button class="button" type="default" @click="logOut">退出登陆</button>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				list: [{
					icon: '../../static/password.png',
					title: '修改密码'
				}, {
					icon: '../../static/account.png',
					title: '切换账号'
				}, {
					icon: '../../static/notice.png',
					title: '通知公告（可点击）'
				}, {
					icon: '../../static/about-us.png',
					title: '关于我们'
				}]
			}
		},
		methods: {
			logOut() {
				console.log('退出登陆')
			},
			toUserInfo() {
				uni.navigateTo({
					url: 'detail'
				});
			},
			toSomePage(item) {
				let title = item.title;
				if (title == '修改密码') {

				} else if (title == '切换账号') {

				} else if (title == '通知公告（可点击）') {
					uni.navigateTo({
						url: 'notice'
					});
				} else if (title == '关于我们') {

				}
			}
		},
		onLoad() {
		}
	}
</script>

<style scoped lang="scss">
	.page-wrapper {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		background-color: #F4F5F7;
		overflow: hidden;
		.page-header {
			position: relative;
			image {
				width: 100%;
			}
			.header-content {
				padding: 0 48rpx;
				position: absolute;
				bottom: 40rpx;
				display: flex;
				align-items: center;
				width: 100%;
				.content-left image {
					width: 104rpx;
				}
				.content-center {
					color: #FFFFFF;
					margin-left: 32rpx;
					font-weight: 400;
					.top {
						font-size: 16px;

					}
					.bottom {
						font-size: 14px;
						margin-top: 10rpx;
					}
				}
				.content-arrow {
					flex: 1;
					text-align: right;
				}
			}
		}
		.operate-list {
			margin-top: 20rpx;
			background-color: #FFFFFF;
			.list-item {
				display: flex;
				padding-left: 48rpx;
				align-items: center;
				.item-icon image {
					width: 32rpx;
					height: 32rpx;
				}
				.border {
					border-top: 1px solid #DCDEE2;
				}
				.item-content {
					flex: 1;
					margin-left: 20rpx;
					display: flex;
					align-items: center;
					padding-right: 48rpx;
					.item-content-title {
						flex: 1;
						padding-left: 12rpx;
						font-size: 14px;
						font-weight: 400;
						color: #17233D;
						line-height: 100rpx;
					}
					.item-right {
						font-size: 14px;
						color: #C5C8CE;
					}
				}
			}
		}
		.button-wrapper {
			display: flex;
			flex: 1;
			flex-direction: column-reverse;
			padding-bottom: 160rpx;
			.button {
				margin: 200rpx auto;
				height: 72rpx;
				line-height: 72rpx;
				font-size: 32rpx;
				border-radius: 36rpx;
				color: #FFFFFF;
				width: 74%;
				background: #5476FD;
			}
		}
	}
</style>
