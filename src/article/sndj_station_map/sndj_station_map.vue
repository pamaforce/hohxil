<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../../static/bg1.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="station1" :url="path"></free-audio>
      </view>
	  <text>进入展厅的右手处，可以看到悬挂着一副关于可可西里保护区的地图。下面的语音将会介绍关于五大保护站的主要工作及藏羚羊迁徙的路径。</text>
    </view>
  </view>
</template>

<script>
import freeAudio from "@/components/free-audio/free-audio.vue";
export default {
  components: {
    freeAudio,
  },
  data() {
    return {
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E7%B4%A2%E5%8D%97%E8%BE%BE%E6%9D%B0%E4%BF%9D%E6%8A%A4%E7%AB%99%E5%9C%B0%E5%9B%BE.m4a?raw=true",
    };
  },
  onLoad() {
    uni.$emit("stop");
  },
  onHide() {
    uni.$emit("stop");
  },
  onUnload() {
  	uni.$emit("stop");  
  },
  methods: {},
};
</script>