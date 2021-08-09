<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="/static/scene/wdl_station.jpg"></image>
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
      path: "/static/audio/example.mp3",
    };
  },
  onLoad() {
    uni.$emit("stop");
  },
  onHide() {
    uni.$emit("stop");
  },
  methods: {},
};
</script>