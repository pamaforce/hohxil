<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/bg4.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="station1" :url="path"></free-audio>
      </view>
	  <text>展厅入口的正对面，大家可以看到一张“巡山反盗猎”的图片。下面的语音将会介绍保护站的工作人员们在巡山任务中的经历与故事。</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E5%B7%A1%E5%B1%B1%E8%BF%87%E7%A8%8B%E4%B8%AD%E7%9A%84%E9%82%A3%E4%BA%9B%E6%95%85%E4%BA%8B%E4%B8%8E%E7%B2%BE%E7%A5%9E.m4a?raw=true",
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