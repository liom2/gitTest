<template>
	<view class="videoList">
		<view class="swiperBox">
			<!-- :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" -->
			<swiper class="swiper" :vertical="true">
				<swiper-item v-for="item of list" :key="item.id">
					<view class="swiper-item">
						<video-player :video="item"></video-player>
					</view>
					<view class="left-box">
						<list-left></list-left>
					</view>
					<view class="right-box">
						<list-right></list-right>
					</view>
				</swiper-item>
			
			</swiper>
		</view>
	</view>
</template>

<script>
	import videoPlayer from './videoPlayer.vue'
	import listLeft from './listLeft.vue'
	import listRight from './listRight.vue'
	export default {
		name:"videoList",
		components:{
			videoPlayer,
			listLeft,
			listRight
		},
		data() {
			return {
				list:[
					{
						id:1,
						src:'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4'
						// src:require('../static/video/1-1.mp4')
					},
					{
						id:2,
						// src:require('static/video/b.mp4')
						src:'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4'
					},
					{
						id:3,
						// src:require('../static/video/c.mp4')
						src:'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4'
					},
					{
						id:4,
						// src:require('../static/video/d.mp4')
						src:'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4'
					}
				]
			};
		}
	}
</script>

<style>
	.videoList{
		height: 100%;
		width: 100%;
		
	}
	.swiperBox{
		height: 100%;
		width: 100%;
	}
	.swiper{
		height: 100%;
		width: 100%;
	}
	.swiper-item{
		height: 100%;
		width: 100%;
		z-index: 19;
	}
	.left-box{
		z-index: 20;
		position: absolute;
		bottom:50rpx;
		left:10rpx;
	}
	.right-box{
		z-index: 20;
		position: absolute;
		bottom:500rpx;
		right:10rpx;
		color: #007AFF;
	}
</style>
