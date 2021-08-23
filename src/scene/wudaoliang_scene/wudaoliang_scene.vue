<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/wdl_station.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="scene10" :url="path"></free-audio>
      </view>
      <text
        >五道梁地区气候全年皆为冬季，最热月（7月）平均气温为5.5℃。自然条件极为恶劣，故民间有“到了五道梁，哭爹又喊娘”，“纳赤台得了病，五道梁要了命”等谚语流传。但由于这一带土壤含汞量较高，植被较少，空气中含氧量相对更低，一般高原反应会在五道梁处非常显现，很多人到了五道梁都不能适应。所以通常认为五道梁是进高原的门槛。</text
      >
      <text>地理位置：青海省玉树藏族自治州治多县109国道北50米</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E4%BA%94%E9%81%93%E6%A2%81.m4a?raw=true",
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