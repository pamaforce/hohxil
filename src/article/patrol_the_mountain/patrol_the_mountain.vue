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
      path: "https://github.com/cjdjczym/trans/blob/main/audio/patrolthemountain.m4a?raw=true",
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