<template>
	<view class="firstNav">
		<view class="iconfont icon-sousuo icon">
			
		</view>
		<view class="middle">
			<view class="text">
				推荐
			</view>
			<view class="text">
				同城
			</view>
		</view>
	</view>
	
</template>

<script>
	export default {
		name:"first-nav",
		data() {
			return {
				
			};
		}
	}
</script>

<style>
	.firstNav{
		width: 100%;
		position: fixed;
		top:46rpx;
		left: 0;
		height: 65rpx;
		line-height: 65rpx;
		margin: 0 auto;
		z-index: 20;
	}
	.icon{
		position: absolute;
		top: 0;
		left: 0;
		color: #FFFFFF;
		width: 20%;
		text-align: center;
		font-size: 15rpx;
	}
	.middle{
		text-align: center;
	}
	.text{
		display: inline;
		color: #FFFFFF;
		margin: 0 10rpx;
	}
</style>
