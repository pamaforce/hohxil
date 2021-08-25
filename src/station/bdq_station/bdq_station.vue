<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/bdq_1.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="station1" :url="path"></free-audio>
      </view>
      <view class="detail-h1">保护站简介：</view>
      <text
        >可可西里管理局的不冻泉保护站是这里最醒目的建筑，也是建设最早的保护站，实际上只是在路两侧有一排房子。对面一处终年不冻的泉水为地名做了最好的诠释。不冻泉车站位于可可西里保护区东侧、三江源自然保护区西侧，海拔4601米，往前开行就进入了青藏铁路最为震撼的长江源地段，这块苍茫大地依然保留古老和原始的自然面貌。</text
      >
      <view class="detail-h1">地理位置：</view>
      <text>青海省玉树藏族自治州曲麻莱县109国道北50米</text>
      <view class="detail-h1">周边：</view>
      <text
        >有三家饭店（民和面片手抓美食城、三江源饭店、兰州拉面手工拌面）、两家客栈（扎西客栈、永峰宾馆）以及一个加油站（中国石油不冻泉加油站）</text
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
      path: "https://github.com/cjdjczym/trans/blob/main/audio/bdqstation.aac?raw=true",
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