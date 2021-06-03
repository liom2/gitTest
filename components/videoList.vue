<template>
	<view class="videoList">
		<view class="swiperBox">
			<!-- :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" -->
			<swiper class="swiper" :vertical="true" @change="change"
				@touchstart="touchstart"
				@touchend="touchend">
				<swiper-item v-for="(item,index) of list" :key="item.id">
					<view class="swiper-item">
						<video-player @changeClick="changeClick" 
						ref="player" :video="item"
						:index="index">
						</video-player>
					</view>
					<view class="left-box">
						<list-left :item="item"></list-left>
					</view>
					<view class="right-box">
						<list-right :item="item" ref="right"></list-right>
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
	var timer=null;
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
						src:'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4',
						author:"joke",
						title:"演员",
						music:"@该配合你演出的我演视而不见@",
						loveNum:13,
						commentNum:34,
						shareNum:66
					},
					{
						id:2,
						// src:require('static/video/b.mp4')
						src:'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4',
						author:"joke",
						title:"丑八怪",
						music:"@有人用一滴泪...@",
						loveNum:43,
						commentNum:23,
						shareNum:854
					},
					{
						id:3,
						// src:require('../static/video/c.mp4')
						src:'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4',
						author:"joke",
						title:"认真的雪",
						music:"@雪下得那么深，下得那么认真...@",
						loveNum:54,
						commentNum:76,
						shareNum:345
					},
					{
						id:4,
						// src:require('../static/video/d.mp4')
						src:'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4',
						author:"joke",
						title:"小幸运",
						music:"@雨滴落在青青草地...@",
						loveNum:56,
						commentNum:547,
						shareNum:45
					}
				],
				pageStartY:0,
				pageEndY:0,
				page:0
			};
		},
		methods:{
			change(res){
				clearTimeout(timer);
				this.page=res.detail.current;
				timer=setTimeout(()=>{
					if(this.pageStartY > this.pageEndY){
						this.$refs.player[this.page].player();
						this.$refs.player[this.page-1].pause();
						this.pageStartY=0;
						this.pageEndY=0;
					}else{
						this.$refs.player[this.page].player();
						this.$refs.player[this.page+1].pause();
						this.pageStartY=0;
						this.pageEndY=0;
					}
				},1);
			},
			touchstart(res){
				this.pageStartY=res.changedTouches[0].pageY;
			},
			touchend(res){
				this.pageEndY=res.changedTouches[0].pageY;
			},
			changeClick(){
				console.log("双击点赞");
				this.$refs.right[0].change();
			}
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
		bottom:200rpx;
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
