<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="/static/scene/qingzang_1.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="scene7" :url="path"></free-audio>
      </view>
      <text
        >青藏公路东起青海省西宁市，西止西藏拉萨市。世界上海拔最高、线路最长的柏油公路，也是目前通往西藏里程较短、路况最好且最安全的公路。沿途景观比较大气磅礴且丰富。可看到草原、盐湖、戈壁、高山、荒漠等景观。沿线风光无限，青海湖、格尔木、唐古拉山口、那曲皆在路线中，这条西藏的生命线也是通往美丽的青藏高原的自驾旅游线。</text
      >
      <image src="/static/scene/qingzang_2.jpg"></image>
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