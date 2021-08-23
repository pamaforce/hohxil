<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/gdjw.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="scene4" :url="path"></free-audio>
      </view>
      <text
        >尕朵觉沃多称尕朵觉悟，属玉树州称多县尕朵乡，是玉树人自视为其守护神的千古名山。</text
      >
      <text
        >尕朵觉沃是一座神山，和西藏的冈仁波齐、云南的梅里雪山和青海的阿尼玛卿山并称为藏传佛教四大神山。整个尕朵觉沃是由一系列千姿百态的山峰组成的群山体，主峰海拔5470米，平均海拔4900米。其主峰山势雄伟、险峻，其他山峰则十分象形，奇特的山形似鬼斧神工，造就了无数美丽的传说。</text
      >
      <text
        >尕朵觉沃意为“上康区主神”，它是吐蕃赞普赤松德赞供奉的藏区神山之一，是长江流域众多神山之王，是造福玉树地区的非凡神山，也是传说中的英雄格萨尔王祭妃的神灵。传说，“尕朵觉沃”是一位智勇双全的大将军，他统率着将士们捍卫美丽富饶的“多堆”，使人们安居乐业，人畜两旺。</text
      >
      <text>地理位置：青海省玉树藏族自治州称多县尕朵乡</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E5%B0%95%E6%9C%B5%E8%A7%89%E6%B2%83.m4a?raw=true",
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