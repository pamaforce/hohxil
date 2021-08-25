<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/sanjiangyuan.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="scene8" :url="path"></free-audio>
      </view>
      <text
        >三江源地区位于我国青海省南部，平均海拔3500～4800米，是世界屋脊——青藏高原的腹地，为孕育中华民族、中南半岛悠久文明历史的世界著名江河：长江、黄河和澜沧江（国外称湄公河）的源头汇水区。地理位置为北纬31°39'～36°12'东经89°45'～102°23'，行政区域涉及包括玉树、果洛、海南、黄南四个藏族自治州的16个县和格尔木市的唐古拉乡，总面积为30.25万平方公里，约占青海省总面积的43%，占16县1乡总面积的97%。现有人口55.6万人，其中藏族人口占90%以上，其他还有汉、回、撒拉、蒙古等民族。</text
      >
      <text
        >2018中国西北旅游营销大会暨旅游装备展上，入围“神奇西北100景”榜单。</text
      >
      <text
        >三江源地区是世界上高海拔生物多样性最集中的地区之一。也是世界上水资源最为丰富的地区之一，因此被誉为“中华水塔”。</text
      >
      <text>地理位置：北纬31°39'～36°12'东经89°45'～102°23'</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/audio/sanjiangyuanscene.m4a?raw=true",
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