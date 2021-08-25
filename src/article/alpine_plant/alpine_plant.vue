<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/bg7.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="station1" :url="path"></free-audio>
      </view>
	  <text>在展厅的最左手边，大家可以看到陈列着一张关于高寒植物的图片。下面的语音将会介绍一些高寒植物的知识。</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/audio/alpineplant.m4a?raw=true",
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