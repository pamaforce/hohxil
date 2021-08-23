<template>
  <view>
    <view class="detail-warpper">
      <image class="detail-top-img" src="../static/bg3.jpg"></image>
      <view class="detail-audio">
        <free-audio :audioId="station1" :url="path"></free-audio>
      </view>
	  <text>进入动物标本厅内，我们可以看到杰森 索南达杰的生平。下面的语音将会介绍索南达杰在可可西里的故事。</text>
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
      path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E7%B4%A2%E5%8D%97%E8%BE%BE%E6%9D%B0%E7%9A%84%E6%95%85%E4%BA%8B.m4a?raw=true",
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