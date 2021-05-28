<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			//隐藏tabBar
			//uni.hideTabBar();
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	.page{
		
	}
	html,body{
		width: 100%;
		height: 100%;
	}
	
	/*每个页面公共css */
	@font-face {
	  font-family: "iconfont"; /* Project id 2562349 */
	  src: url('~@/static/fonts/iconfont.woff2?t=1622170820558') format('woff2'),
	       url('~@/static/fonts/iconfont.woff?t=1622170820558') format('woff'),
	       url('~@/static/fonts/iconfont.ttf?t=1622170820558') format('truetype');
	}
	
	.iconfont {
	  font-family: "iconfont" !important;
	  font-size: 16px;
	  font-style: normal;
	  -webkit-font-smoothing: antialiased;
	  -moz-osx-font-smoothing: grayscale;
	}
	
	.icon-pinglun:before {
	  content: "\e601";
	}
	
	.icon-shoucangaixinxin:before {
	  content: "\e61a";
	}
	
	.icon-fenxiang:before {
	  content: "\e612";
	}
	
	.icon-sousuo:before {
	  content: "\e60f";
	}
	
	.icon-fanhui:before {
	  content: "\e610";
	}
	
	.icon-jiahao:before {
	  content: "\e613";
	}

</style>
