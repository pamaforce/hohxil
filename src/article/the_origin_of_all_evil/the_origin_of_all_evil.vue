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
      path: "https://github.com/cjdjczym/trans/blob/main/audio/theoriginofallevil.m4a?raw=true",
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