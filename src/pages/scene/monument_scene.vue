<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="/static/scene/monument.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="scene6" :url="path"></free-audio>
      </view>
      <text
        >杰桑·索南达杰是治多县索加乡人，为保护野生动物曾先后12次进入可可西里无人区进行野生动植物资源调查，被誉为可可西里野生动物保护第一人。1994年1月，索南达杰和他的队员抓获了20名非法猎杀藏羚羊的盗猎分子，在押送歹徒途中遭到歹徒袭击。为保护藏羚羊，索南达杰与18名持枪偷猎者在无人区对峙，最终丧生在可可西里的严寒之中。当人们在无人区找到他的遗体时，他仍旧保持着换子弹的姿势。纪念碑上详细描述了可可西里的英雄——杰桑·索南达杰的一生。</text
      >
      <text>地理位置：青海省玉树藏族自治州曲麻莱县109国道西100米</text>
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