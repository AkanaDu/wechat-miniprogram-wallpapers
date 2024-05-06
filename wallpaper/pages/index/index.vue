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
	} 
</style>
