<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/zhuonai_lake.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="scene11" :url="path"></free-audio>
      </view>
      <text
        >卓乃湖是一个音译过来的地名，藏族同胞将藏羚羊叫作：Zu
        ，卓乃湖就是藏羚羊聚集的地方。可可西里的藏羚羊占了全球藏羚的绝大多数，而可可西里的绝大多数母羚羊在每年7、8月份都会集中到卓乃湖以南一片不大的草原产仔，9月份返回越冬地与公羊合群。在产仔期，卓乃湖南岸会有几万头母羚羊聚集，有的已产下活蹦乱跳的羊羔，有的正在期盼小生命的降生。5404米的好日阿日旧雪山下，万羊奔腾涌起阵阵热浪，空气中充满柔和缠绵的藏羚叫声，壮观景象令人叹为观止。</text
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
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E5%8D%93%E4%B9%83%E6%B9%96.m4a?raw=true",
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