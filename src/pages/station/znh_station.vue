<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="/static/station/znh_1.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="station5" :url="path"></free-audio>
      </view>
      <view class="detail-h1">保护站简介：</view>
      <text
        >卓乃湖保护站，是位于保护区腹地卓乃湖旁流动的帐房保护站，卓乃湖站点海拔4790米，是藏羚羊集中产仔的地区，距青藏公路180公里。</text
      >
      <view class="detail-h1">保护站工作内容：</view>
      <text
        >在环卓乃湖地区，是藏羚羊的大产房，这里也是中国最与世隔绝的地方之一，就在离卓乃湖几公里远的地方，一处被钢板包围着的四方形建筑显得格外醒目，那里就是卓乃湖保护站。卓乃湖保护站是一个季节性的保护站，最早的时候只有一顶白色的帐篷，现在则完善发展成了相对较完整的营地，物资储备较为充足。每年五月份，这里会从其他四个保护站各抽调一名队员前来驻扎。等到五月底六月初，近四万只藏羚羊会来到卓乃湖产仔，这段时间，保护站会组织定期巡山，监测藏羚羊数量，为藏羚羊提供一个安静的成长环境。</text
      >
      <image src="/static/station/znh_2.jpg"></image>
      <text
        >卓乃湖保护站工作人员共六名，平时的工作就是监测、巡护、救助藏羚羊，所救的藏羚羊在喂养十到十五天，就会送到索南达杰保护站。（源于副站长郭雪虎的采访）</text
      >
      <text
        >保护站平时的工作枯燥而辛苦，巡山队员需要长期忍受与世隔绝的辛苦，这里没有信号，供电也是时断时续，日常的用水也是附近的河水，但是就因为这片净土，因为这里美丽的生灵，保护站的队员们日复一日的坚守着，从未放弃</text
      >
      <view class="detail-h1">地理位置：</view>
      <text>卓乃湖周边</text>
      <view class="detail-h1">保护站站长：</view>
      <text>秋培扎西，郭雪虎（副站长）</text>
      <view class="detail-h1">保护站周边：</view>
      <text>卓乃湖</text>
      <image src="/static/station/znh_3.jpg"></image>
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