<template>
	<view class="cityContent">
		<view class="conlation">
			<view class="iconfont icon-dingwei_huaban1 conlation-left">
				自动定位:南京
			</view>
			<view class="conlation-right">
				切换<text class="iconfont icon-you"></text>
			</view>
		</view>
		<view class="video-list">
			<view class="item">
				<view class="video">
					<video 
					style="width: 100%;height: 100%;" 
					objectFit="contain"
					src="https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4" controls></video>
				</view>
				<view class="img">
					<image class="image-box" src="../static/img/author.jpg" mode=""></image>
				</view>
			</view>
			
			<view class="item">
				<view class="video">
					<video 
					style="width: 100%;height: 100%;" 
					objectFit="contain"
					src="https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4" controls></video>
				</view>
				<view class="img">
					<image class="image-box" src="../static/img/author.jpg" mode=""></image>
				</view>
			</view>
			<view class="item">
				<view class="video">
					<video 
					style="width: 100%;height: 100%;" 
					objectFit="contain"
					src="https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4" controls></video>
				</view>
				<view class="img">
					<image class="image-box" src="../static/img/author.jpg" mode=""></image>
				</view>
			</view>
			<view class="item">
				<view class="video">
					<video 
					style="width: 100%;height: 100%;" 
					objectFit="contain"
					src="https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4" controls></video>
				</view>
				<view class="img">
					<image class="image-box" src="../static/img/author.jpg" mode=""></image>
				</view>
			</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		name:"cityContent",
		data() {
			return {
				
			};
		}
	}
</script>

<style>
	.cityContent{
		width: 100%;
		background:#000000;
		z-index: 18;
	}
	.conlation{
		width: 100%;
		height: 40rpx;
		padding-top: 16%;
		overflow: hidden;
		color: #aaaaaa;
	}
	.conlation-left{
		float: left;
		font-size: 25rpx;
		padding-left: 15rpx;
	}
	.conlation-right{
		float: right;
		font-size: 25rpx;
		padding-right: 15rpx;
	}
	.video-list{
		width: 100%;
		overflow: auto;
		background: #000000;
	}
	.item{
		width: 50%;
		float: left;
		position: relative;
	}
	.video{
		width: 92%;
		margin-left: 4%;
		height: 600rpx;
	}
	.img{
		position: absolute;
		bottom: 7rpx;
		right:15rpx
	}
	.image-box{
		width: 30rpx;
		height: 30rpx;
		border-radius: 50%;
	}
</style>
