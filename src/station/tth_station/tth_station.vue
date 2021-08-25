<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/tth_1.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="station3" :url="path"></free-audio>
      </view>
      <view class="detail-h1">保护站简介：</view>
      <text
        >沱沱河保护站，位于青藏公路3120公里处，为保护区的南大门，距格尔木市360余公里。建于2005年10月。各保护站除负责各自辖区内野生动物和生态环境保护，开展巡山反盗猎斗争，此外，还担负着接应和支援主力巡山队的后勤保障工作，在青藏公路进行路查和向保护区周边地区群众进行宣传教育的任务。</text
      >
      <view class="detail-h1">地理位置：</view>
      <text>治多县109国道北50米。</text>
      <view class="detail-h1">保护站站长：</view>
      <text>文尕松宝、普措才仁（副站长）</text>
      <view class="detail-h1">保护站周边：</view>
      <text
        >果永联合加油站、沱沱河森林派出所、夏河拉卜楞综合批发部、八十二道班</text
      >
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
      path: "https://github.com/cjdjczym/trans/blob/main/audio/tthstation.m4a?raw=true",
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