<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/tuotuo.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="scene9" :url="path"></free-audio>
      </view>
      <text
        >沱沱河位于青海省格尔木市南域唐古拉山镇，在可可西里山脉以南。它从格拉丹东雪山的姜根迪如冰川发源时，是一些冰川、冰斗的融水汇成的小溪流，这时的水面宽只有3米，深只有20多厘米，然后向北流过9千多米长的距离，在巴冬山下汇集了尕恰迪如岗雪山的冰川融水，经过一条长约15公里的谷地，继续向北，分成了两条宽4米和6米的小河，小河两边的谷地中还有许多密如蛛网的水流，这里是沱沱河的上源。在这片谷地的出口，河谷突然下切，形成了一条长约5公里的陡峭峡谷，高达20多米。众多河流交汇后，形成了河道开阔，水流交织的长江西源——沱沱河。沱沱河行政上属格尔木市（附区）唐古拉山镇管辖。</text
      >
      <text>地理位置：格尔木市</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/audio/tuotuoscene.aac?raw=true",
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