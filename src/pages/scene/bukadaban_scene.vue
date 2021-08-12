<template>
  <view>
    <view class="detail-warpper">
      <image
        class="detail-top-img"
        src="/static/scene/bkdb_mountain.jpg"
      ></image>
      <view class="detail-audio">
        <free-audio :audioId="scene1" :url="path"></free-audio>
      </view>
      <text
        >布喀达坂峰（又称新青峰）：是昆仑山脉的最高峰，海拔7765米，峰区有巨大的冰帽冰川，平均雪线高度5550米，冰川面积243.6平方公里有53条冰川，其中最大的布喀冰川，长24.2公里。平卧于东南坡，形成尾宽3000米的宽尾冰川，冰舌末端4910米，在冰舌前缘平坦谷地有近2000米的范围内，有残留的冰塔状孔冰和冰碛残留，形态千奇百怪，就像一座魔鬼城堡。</text
      >
      <text>地理位置：青海省玉树藏族自治州治多县</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E5%B8%83%E5%96%80%E8%BE%BE%E5%9D%82.aac?raw=true",
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