<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/bg5.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="station1" :url="path"></free-audio>
      </view>
	  <text>在展厅的左手处，大家可以看到保护站的工作人员对小藏羚羊进行救助的图片。下面的语音将会介绍保护站工作人员们照顾小藏羚羊的日常。图片下方放置着一块展板，上面是拍摄到的已经脱毛的成年藏羚羊。</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E8%97%8F%E7%BE%9A%E7%BE%8A%E7%9A%84%E5%85%BB%E6%8A%A4.m4a?raw=true",
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