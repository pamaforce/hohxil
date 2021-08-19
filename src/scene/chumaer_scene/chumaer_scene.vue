<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/chumaer.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="scene3" :url="path"></free-audio>
      </view>
      <text
        >楚玛尔河（曲麻河）：长江源的北源，位于青海省玉树藏族自治州西部（青藏公路之西属治多县西部北麓河乡，之东属曲麻莱县），发自可可西里山黑脊山南麓。“楚玛尔”为藏语，意为“红水河”，又译为曲麻莱河、曲麻河、曲麻曲。</text
      >
      <text
        >流域呈狭长形，横卧长江源区域北部，汇集昆仑山南坡来水汇入通天河，流域面积20800平方公里。楚玛尔河源头地区的北部与西金乌兰湖、可可西里湖等内陆湖区相邻。地势平坦，海拔5000～5150米，山岭比高约200米，受构造控制呈北西西走向。由于气候干燥，降水量仅
        250～300毫米，蒸发量为1800毫米左右，所以地面多干涸沟谷，植被稀少，砂砾广布，湖泊萎缩，风积地形发育。</text
      >
      <text>楚玛尔河水系是昆仑山脉东段的南坡一带的主要水系。</text>
      <text
        >楚玛尔河属长江源自然保护区，上游区域是可可西里保护区的中心地带。</text
      >
      <text>青藏铁路在此有楚玛尔河站。</text>
      <text>地理位置：青海省玉树藏族自治州治多县/曲麻莱县</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E6%A5%9A%E7%8E%9B%E5%B0%94%E6%B2%B3.m4a?raw=true",
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