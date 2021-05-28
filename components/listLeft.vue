<template>
	<view class="listLeft">
		<view class="author">
			薛之谦
		</view>
		<view class="title">
			演员
		</view>
		<view class="box">
			<view class="music">
				@该配合你演出的我演视而不见@
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		name:"listLeft",
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
		height: 35rpx;
		line-height: 35rpx;
		font-size: 17rpx;
	}
	.title{
		line-height: 22rpx;
		font-size: 12rpx;
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
		font-size: 12rpx;
		width: 190rpx;
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
