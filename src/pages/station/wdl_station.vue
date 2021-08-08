<template>
	<view>
		<view class="detail-warpper">
			<image class="detail-top-img" src="/static/station/wdl_1.jpg"></image>
			<view class="detail-audio">
				<free-audio :audioId='station4' :url='path'></free-audio>
			</view>
			<view class="detail-h1">保护站简介：</view>
			<text>五道梁保护站是和五道梁镇分开的，距离有三十多公里，是条件最艰苦的保护站，如果将保护站建在镇上，各方面条件会好很多。之所以建站在此地，便是因为保护站对面就是藏羚羊迁徙必经的桥洞（乌北大桥）。迁徙季节工作人员每天在此观测藏羚羊群的动向，保护羊群顺利通过青藏铁路不受危险。尽管条件艰苦，但他们无怨无悔。每天护送羊群过马路后，保护站工作人员还要记录藏羚羊群的迁徙数量，以进行科学的研究。</text>
			<view class="detail-h1">地理位置：</view>
			<text>青海省玉树藏族自治州治多县109国道北50米。</text>
			<view class="detail-h1">保护站站长：</view>
			<text>文尕公宝、孟克（副站长）</text>
			<view class="detail-h1">保护站周边：</view>
			<text>可可西里藏羚羊观景台、十四公里外大约有七家饭店。</text>
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