<template>
	<view class="listRight">
		<view class="author-img">
			<image class="img" src="../static/img/author.jpg"></image>
			<view class="iconfont icon-jiahao add" v-show="show" @click="hide">
				
			</view>
		</view>
		<view class="iconfont icon-shoucangaixinxin right-box" :style="color" @click="changeColor">
			
		</view>
		<view class="number">
			{{item.loveNum}}
		</view>
		<view class="iconfont icon-pinglun right-box">
			
		</view>
		<view class="number">
			{{item.commentNum}}
		</view>
		<view class="iconfont icon-fenxiang right-box">
			
		</view>
		<view class="number">
			{{item.shareNum}}
		</view>
		<view class="around">
			<image class="img" src="../static/img/author.jpg"></image>
		</view>
	</view>
</template>

<script>
	export default {
		name:"listRight",
		props:['item'],
		data() {
			return {
				show:true,
				color:''
			};
		},
		methods:{
			hide(){
				this.show=false;
			},
			changeColor(){
				this.color=this.color===''?"color:red;":"";
			},
			change(){
				this.color="color:red;";
			}
		}
	}
</script>

<style>
	.listRight{
		width: 50rpx;
		margin: 0 auto;
		color: #FFFFFF;
	}
	.author-img{
		height: 50rpx;
		width: 50rpx;
		border-radius: 50%;
		border: 2rpx solid #FFFFFF;
		position: relative;
	}
	.img{
		height: 50rpx;
		width: 50rpx;
		border-radius: 50%;
	}
	.right-box{
		width: 50rpx;
		height: 40rpx;
		margin-top:13rpx;
		text-align: center;
		line-height: 40rpx;
		color: #FFFFFF;
		font-size: 33rpx;
	}
	.number{
		font-size: 10rpx;
		text-align: center;
		color: #FFFFFF;
	}
	.around{
		height: 50rpx;
		width: 50rpx;
		margin-top:15rpx;
		animation: rotate 1.5s linear 0.2s infinite;
	}
	.add{
		width: 18rpx;
		height: 18rpx;
		border-radius: 50%;
		background: red;
		position: absolute;
		bottom: -9rpx;
		left: 16rpx;
		text-align: center;
		line-height: 18rpx;
		color: #FFFFFF;
		font-size: 9rpx;
	}
	
	@keyframes rotate{
		0%{
			transform: rotate(0deg);
		}
		100%{
			transform: rotate(360deg);
		}
	}
</style>
