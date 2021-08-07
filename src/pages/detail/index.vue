<template>
	<view>
		<image src="../../static/example.jpg" class="top-img-class"></image>
		<view class="top-items-class">
			<free-audio startPic='/static/play.png' endPic='/static/stop.png' :audioId='audio1' :url='path'></free-audio>
		</view>
	</view>
</template>

<script>
	import freeAudio from '@/components/free-audio/free-audio.vue'
	export default {
		components: {
			freeAudio
		},
		data() {
			return {
				path: '/static/audio/example.mp3'
			};
		},
		onLoad() {
			uni.$emit('stop')
		},
		onHide() {
			uni.$emit('stop')
		},
		methods: {},
	};
</script>

<style>
	.top-img-class {
		margin: 10rpx;
		width: 100%;
		height: 500rpx; 
	}
	.top-items-class {
		display: flex;
		justify-content: center;
	}
</style>
