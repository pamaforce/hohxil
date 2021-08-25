<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/ceh_lake.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="scene2" :url="path"></free-audio>
      </view>
      <text
        >察尔汗盐湖，是中国青海省西部的一个盐湖，与茶卡盐湖齐名，位于柴达木盆地南部，地跨格尔木市和都兰县，由达布逊湖以及南霍布逊、北霍布逊、涩聂等盐池汇聚而成，总面积5856平方公里，格尔木河、柴达木河等多条内流河注入该湖。由于水分不断蒸发，盐湖上形成坚硬的盐盖，青藏铁路和青藏公路直接修建于盐盖之上，察尔汗盐湖蕴藏有丰富的氯化钠、氯化钾、氯化镁等无机盐，总储量达20多亿吨，为中国矿业基地之一。有著名的万丈盐桥。</text
      >
      <text>地理位置：青海省海西蒙古族藏族自治州格尔木市北60公里</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/audio/chaerhanscene.m4a?raw=true",
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