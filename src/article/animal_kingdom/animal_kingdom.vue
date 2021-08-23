<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/bg2.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="station1" :url="path"></free-audio>
      </view>
	  <text>在地图的右边，大家可以看到悬挂着这张“动物王国”的图片。下面的语音将会介绍可可西里保护站的各类野生动物，展厅内陈列着对应的标本，游客们可以自行对号入座。</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E5%8A%A8%E7%89%A9%E7%8E%8B%E5%9B%BD.m4a?raw=true",
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