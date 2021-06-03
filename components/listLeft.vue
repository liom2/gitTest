<template>
	<view class="listLeft">
		<view class="author">
			{{item.author}}
		</view>
		<view class="title">
			{{item.title}}
		</view>
		<view class="box">
			<view class="music">
				{{item.music}}
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		name:"listLeft",
		props:[
			'item'
		],
		data() {
			return {
				
			};
		}
	}
</script>

<style>
	.listLeft{
		height: 150rpx;
		width: 150rpx;
		margin-left:10rpx;
		color: #FFFFFF;
	}
	.author{
		padding-top: 20rpx;
		height: 35rpx;
		line-height: 35rpx;
		font-size: 25rpx;
	}
	.title{
		line-height: 22rpx;
		font-size: 20rpx;
		width: 100%;
		word-wrap: break-word;
	}
	.box{
		width: 100rpx;
		overflow: hidden;
	}
	.music{
		height: 35rpx;
		line-height: 35rpx;
		font-size: 20rpx;
		width: 350rpx;
		animation: music 4s linear 0.2s infinite;
	}
	
	@keyframes music{
		from{
			transform: translate3d(80%,0,0);
		}
		to{
			transform: translate3d(-80%,0,0);
		}
	}
</style>
