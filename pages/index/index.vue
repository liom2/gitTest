<template>
	<view class="content">
		<first-nav></first-nav>
		<video-list></video-list>
		<tab></tab>
	</view>
</template>

<script>
	import tab from '../../components/tab.vue'
	import firstNav from '../../components/first-nav.vue'
	import videoList from '../../components/videoList.vue'
	export default {
		components:{
			tab,
			firstNav,
			videoList
		},
		data() {
			return {
				
			}
		},
		onLoad() {

		},
		methods: {
			
		}
	}
</script>

<style>
	.content{
		width: 100%;
		height: 100%;
	}
</style>
