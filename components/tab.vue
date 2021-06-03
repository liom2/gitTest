<template>
	<view class="tab">
		<view class="tab-box">
			首页
		</view>
		<view class="tab-box">
			关注
		</view>
		<view class="tab-box">
			<view class="iconfont icon-jiahao icon-box">
				
			</view>
		</view>
		
		<view class="tab-box">
			消息
		</view>
		<view class="tab-box">
			我
		</view>
	</view>
</template>

<script>
	export default {
		name:"tab",
		data() {
			return {
				
			};
		}
	}
</script>

<style>
	.tab{
		height: 80px;
		width: 100%;
		position: fixed;
		bottom: 0;
		left: 0;
		z-index: 20;
		
	}
	.tab-box{
		float: left;
		width: 20%;
		color: #FFFFFF;
		text-align: center;
		height: 80rpx;
		line-height: 80rpx;
		font-size: 25rpx;
	}
	.icon-box{
		width: 60%;
		height: 30rpx;
		background: #FFFFFF;
		color: #000000;
		margin: 23rpx 20%;
		line-height: 30rpx;
		border-radius: 5rpx;
		font-size: 15rpx;
	}
</style>
