<template>
	<view class="videoPlayer">
		<!-- https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4 -->
		<video id="myVideo" class="videoDiv" :src="video.src"
			@error="videoErrorCallback" controls="true"
			:loop="false" :autoplay="autoPlay"
			objectFit="contain"
			@click="click">
			
		</video>
	</view>
</template>

<script>
	var timer=null;
	export default {
		name:"videoPlayer",
		props:['video','index'],
		data() {
			return {
				play:false,
				dbClick:false,
				autoPlay:false
			};
		},
		onReady(){
			this.videoContext=uni.createVideoContext('myVideo',this);
		},
		created(){
			//console.log("index=="+this.index);
			this.auto();
		},
		methods:{
			videoErrorCallback:function(e) {
				console.log("视频错误信息");
				console.log(e.target.errMsg);
			},
			player(){
				if(this.play===false){
					this.videoContext.seek(0);
					this.videoContext.play();
					this.play=true;
				}
			},
			pause(){
				if(this.play===true){
					this.videoContext.pause();
					this.play=false;
				}
			},
			playThis(){
				if(this.play===false){
					this.videoContext.play();
					this.play=true;
				}
			},
			click(){
				clearTimeout(timer);
				this.dbClick= !this.dbClick;
				timer=setTimeout(()=>{
					if(this.dbClick){
						if(this.play===false){
							this.playThis();
						}else{
							this.pause();
						}
					}else{
						this.$emit('changeClick')
					}
					this.dbClick=false;
				},300);
				
			},
			auto(){
				if(this.index===0){
					this.autoPlay=true;
				}
			}
		}
	}
</script>

<style lang="scss">
	.videoPlayer{
		width : 100%;
		height : 100%;
	}
	.videoDiv{
		width : 100%;
		height : 100%;
	}
</style>

<!-- <template>
    <view>
        <view class="page-body">
            <view class="page-section">
                <video id="myVideo" src="https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/360e4b20-4f4b-11eb-8a36-ebb87efcf8c0.mp4" @error="videoErrorCallback" :danmu-list="danmuList"
                    enable-danmu danmu-btn controls></video>

                <view class="uni-list">
                    <view class="uni-list-cell">
                        <view>
                            <view class="uni-label">弹幕内容</view>
                        </view>
                        <view class="uni-list-cell-db">
                            <input @blur="bindInputBlur" class="uni-input" type="text" placeholder="在此处输入弹幕内容" />
                        </view>
                    </view>
                </view>
                <view class="btn-area">
                    <button @tap="bindSendDanmu" class="page-body-button" formType="submit">发送弹幕</button>
                </view>
            </view>
        </view>
    </view>
</template>
<script>
	export default {
		name:"videoPlayer",
	    data() {
	        return {
	            title: 'video',
	            src: '',
	            inputValue: '',
	            danmuList: [{
	                    text: '第 1s 出现的弹幕',
	                    color: '#ff0000',
	                    time: 1
	                },
	                {
	                    text: '第 3s 出现的弹幕',
	                    color: '#ff00ff',
	                    time: 3
	                }
	            ]
	        }
	    },
	    onReady: function (res) {
	        this.videoContext = uni.createVideoContext('myVideo')
	    },
	    methods: {
	        bindInputBlur: function (e) {
	            this.inputValue = e.target.value
	        },
	        bindButtonTap: function () {
	            var that = this
	            uni.chooseVideo({
	                sourceType: ['album', 'camera'],
	                maxDuration: 60,
	                camera: ['front', 'back'],
	                success: function (res) {
	                    this.src = res.tempFilePath
	                }
	            })
	        },
	        bindSendDanmu: function () {
	            this.videoContext.sendDanmu({
	                text: this.inputValue,
	                color: this.getRandomColor()
	            })
	        },
	        videoErrorCallback: function (e) {
	            console.log('视频错误信息:')
	            console.log(e.target.errMsg)
	        },
	        getRandomColor: function () {
	            const rgb = []
	            for (let i = 0; i < 3; ++i) {
	                let color = Math.floor(Math.random() * 256).toString(16)
	                color = color.length == 1 ? '0' + color : color
	                rgb.push(color)
	            }
	            return '#' + rgb.join('')
	        }
	    }
	}
</script>

 -->