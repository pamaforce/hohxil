<template>
	<!-- 音频播放器组件 -->
	<view v-if='url' class='flex justify-between align-center audio' >
		<view class='img'  @click='start(audioId)'>
			<image src='/static/play.png' class='icon' v-show='!status'></image>
			<image src='/static/stop.png' class='icon' v-show='status'></image>
		</view>
		<view class='time'>{{getTime(Math.round(currentTime),Math.round(duration))}}</view>
		<view class='flex-1'>
			<slider @change='changeAudio' :activeColor='activeColor' :backgroundColor='backgroundColor' :min='0' :max='duration.toFixed(0)' :value='currentTime.toFixed(0)' :step='0.1' block-size=15></slider>
		</view>
		<view class='img'  @click='mute()'>
			<image src='/static/not_mute.png' class='icon2' v-show='!muted'></image>
			<image src='/static/is_mute.png' class='icon2' v-show='muted'></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				context: null,
				currentTime: 0,
				duration: 100,
				status: false,
				muted: false
			}
		},
		props: {
			url: String,
			activeColor: {
				type: String,
				default: '#697780'
			},
			backgroundColor: {
				type: String,
				default: '#BFC5C8'
			},
			audioId: [String,Number]
		},
		created() {
			this.context = uni.createInnerAudioContext();
			this.context.src = this.url;
			this.onTimeUpdate();
			this.onCanplay();
			this.onEnded();
			uni.$on('stop',(id)=> {
				if(id && id != this.audioId) {
					this.context.stop();
					this.status = false;
				} else if(!id){
					this.context.stop();
					this.status = false;
				}
			})
		},
		methods: {
			start(id) { //点击播放
				let audioId = id;
				if(this.status) {
					this.context.pause();
				}else {
					uni.$emit('stop',id)
					this.context.play()
				}
				this.status = !this.status;
			},
			mute() {
				if(this.muted) {
					this.context.volume = 1;
				} else {
					this.context.volume = 0;
				}
				this.muted = !this.muted;
			},
			onCanplay() { //进入可播放状态
				this.context.onCanplay(() => {
					this.context.duration;
					setTimeout(()=>{
						this.duration = this.context.duration;
					},1000)
				})
			},
			onTimeUpdate() { //音频播放进度
				this.context.onTimeUpdate(() => {
					this.duration = this.context.duration;
					this.currentTime = this.context.currentTime;
				})
			},
			onEnded() { //播放结束
				this.context.onEnded(()=> {
					this.status = false;
					this.currentTime = 0;
				})
			},
			changeAudio(e) {
				let paused = this.context.paused;
				this.context.pause();
				this.context.seek(e.detail.value)
				if(!paused) {
					this.context.play();
				} 
			},
			getTime(nowTime, totalTime) {
				let m1 = parseInt(nowTime / 60);
				let s1 = nowTime % 60;
				let m2 = parseInt(totalTime / 60);
				let s2 = totalTime % 60;
				return this.towNum(m1) + ':' + this.towNum(s1) + '/' + this.towNum(m2) + ':' + this.towNum(s2);
			},
			towNum(num) {
				if(num >= 10) {
					return num;
				}else {
					return '0' + num;
				}
			}
		}
	}
</script>

<style>
	.audio {
		background: #F4F4F4;
		border-radius: 60rpx;
		padding: 20rpx;
		width: 520rpx;
		height: 100rpx;
	}
	
	.icon {
		width: 65rpx !important;
		height: 65rpx !important;
		padding: 0 0 0 0 !important;
	}
	
	.icon2 {
		width: 45rpx !important;
		height: 45rpx !important;
		padding: 0 10rpx 0 0 !important;
	}
	
	.flex {
		display: flex;
		flex-direction: row;
	}
	
	.justify-between {
		justify-content: between;
	}
	
	.align-center {
		align-items: center;
	}
	
	.flex-1 {
		flex: 1;
	}
	
	.time {
		margin-left: 15rpx;
		margin-right: 3rpx;
		margin-bottom: 3rpx;
	}
	
	.img {
		margin: 5rpx;
	}
</style>
