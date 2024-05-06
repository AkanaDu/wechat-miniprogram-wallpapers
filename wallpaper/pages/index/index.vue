<template>
	<view class="home-layout">
		<view class="banner">
			<swiper indicator-dots indicator-color="rgba(255, 255, 255, 0.5)" indicator-active-color="rgba(255,255,255,1)" autoplay circular>
				<swiper-item v-for="item in 3" :key="item">
					<image src="../../common/images/row.jpg" mode="aspectFill"/>
				</swiper-item>
			</swiper>
		</view>
		<!-- 公告 -->
		<view class="notice">
				<view class="left">
					<uni-icons type="sound-filled" size="20" color="#28b389"></uni-icons>
					<text class="text">公告</text>
				</view>
				<view class="center">
					<swiper vertical autoplay circular>
						<swiper-item v-for="item in 3" :key="item" >
							你好，这里是公告！{{item}}
						</swiper-item>
					</swiper>
				</view>
				<view class="right">
					<uni-icons type="forward" size="20" color="#28b389"></uni-icons>
				</view>
		</view>
		<!-- 公共标题 -->
		<view class="select">
			<common-title>
				<template #name>每日推荐</template>
				<template #custom>
					<view class="date">
						<uni-icons type="calendar" size="18" color="#28b389"></uni-icons>
						<view class="text">
							<uni-dateformat format="dd" :date="Date.now()"></uni-dateformat>日
						</view>
					</view>
				</template>
			</common-title>
			<view class="content">
					<scroll-view scroll-x >
						<view class="box" v-for="item in 8" :key="item">
							<image src="../../common/images/col.jpeg" mode="aspectFill"></image>
						</view>
					</scroll-view>
			</view>
		</view>
		<!-- 专题 -->
		<view class="theme">
			<common-title>
				<template #name>专题精选</template>
				<template #custom>
					<navigator url="" class="more">更多...</navigator>
				</template>
			</common-title>
		</view>
	</view>
</template>

<script setup>
</script>

<style lang="scss" scoped>
	.home-layout {
		.banner {
			width: 750rpx;
			padding: 30rpx 0;
			swiper {
				width: 750rpx;
				height: 340rpx;
				&-item {
					padding: 0 25rpx;
					width: 100%;
					height: 100%;
					image {
						width: 100%;
						height: 100%;
						border-radius: 25rpx;
					}
				}
			}
		}
		.notice {
			width: 700rpx;
			height: 80rpx;
			background: #f9f9f9;
			margin: 0 auto;
			border-radius: 80rpx;
			display: flex;
			line-height: 80rpx;
			.left {
				width: 140rpx;
				display: flex;
				justify-content: center;
				align-items: center;
				.text {
					color: #28b389;
					font-weight: 600;
					font-size: 28rpx;
				}
			}
			.center {
				flex: 1;
				swiper {
					height: 100%;
					&-item {
						height: 100%;
						font-size: 30rpx;
						color: #666;
						overflow: hidden;
						white-space: nowrap;
						text-overflow: ellipsis;
					}
				}
			}
			.right {
				width: 70rpx;
				display: flex;
				justify-content: center;
				align-items: center;
			}
		}
		.select {
			padding-top: 50rpx;
			.date {
				display: flex;
				align-items: center;
				color: #28b389;
				.text {
					margin-left: 5rpx;
				}
			}
			.content {
				width: 725rpx;
				margin-left: 25rpx;
				margin-top: 25rpx;
				scroll-view {
					white-space: nowrap;
					.box {
						width: 200rpx;
						height: 430rpx;
						display: inline-block;
						margin-right: 15rpx;
						image {
							width: 100%;
							height: 100%;
							border-radius: 25rpx;
						}
					}
					.box:last-child {
						margin-right: 25rpx;
					}
				}
			}
		}
		
		.theme {
			padding-top: 50rpx;
			.more{
				font-size: 32rpx;
				color: #888;
			}
		}
	} 
</style>
