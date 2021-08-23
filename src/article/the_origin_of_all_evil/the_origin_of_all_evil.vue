<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/bg6.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="station1" :url="path"></free-audio>
      </view>
	  <text>在“藏羚羊守护”图片的左边，大家可以看到一张“一切罪恶的来源”的照片。下面的语音将会介绍屠杀藏羚羊的起源故事。</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E4%B8%80%E5%88%87%E7%BD%AA%E6%81%B6%E7%9A%84%E8%B5%B7%E6%BA%90.m4a?raw=true",
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