<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/kunlun_1.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="scene5" :url="path"></free-audio>
      </view>
      <text
        >昆仑山山口是青藏公路穿越昆仑山脉的必经之地，咽喉之所，是世界屋脊汽车探险线的必经之地，昆仑六月雪观光的重要景点。昆仑山口属多年冻土区荒漠地貌，山坡谷地生长梅、虎爪耳草、等高原冻土荒漠野生植物。登临山口，巍巍昆仑的千峰万壑如同披着银灰色铠甲的群群奔马，随着风起云涌，滚滚向前。</text
      >
      <text>地理位置：青海省海西蒙古族藏族自治州格尔木市109国道附近</text>
      <image src="../static/kunlun_2.jpg"></image>
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
      path: "https://github.com/cjdjczym/trans/blob/main/audio/kunlunscene.m4a?raw=true",
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