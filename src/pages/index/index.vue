<template>
  <view>
    <view class="header-class">
      <image
        src="../../static/position.png"
        class="top-img-class"
        style="width: 75px"
        @click="toPosition"
      ></image>
      <view style="width: 30px"></view>
      <image
        src="../../static/telephone.png"
        class="top-img-class"
        style="width: 55px"
        @click="setClipboard"
      ></image>
      <view style="width: 30px"></view>
      <image
        src="../../static/aboutus.png"
        class="top-img-class"
        style="width: 83px"
        @click="toAbout"
      ></image>
    </view>
    <view
      class="item-class"
      v-for="(item, i) in lists"
      :key="i"
      @click="toDesc(item.to)"
    >
      <image class="bg-set" :src="item.url"></image>
      <view class="title-class">{{ item.title }}</view>
    </view>
    <u-tabbar :list="list"></u-tabbar>
  </view>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {
          iconPath: "home",
          selectedIconPath: "home-fill",
          text: "主页",
          pagePath: "/pages/index/index",
        },
        {
          iconPath: "/static/guide.png",
          selectedIconPath: "/static/guide-fill.png",
          text: "导览",
          pagePath: "/pages/guide/index",
        },
      ],
      lists: [
        {
          title: "索南达杰保护站地图",
          url: "../../static/bg1.jpg",
          to: "../../article/sndj_station_map/sndj_station_map",
        },
        {
          title: "动物王国",
          url: "../../static/bg2.jpg",
          to: "../../article/animal_kingdom/animal_kingdom",
        },
        {
          title: "索南达杰的故事",
          url: "../../static/bg3.jpg",
          to: "../../article/the_story_of_sndj/the_story_of_sndj",
        },
        {
          title: "巡山过程中的那些故事与精神",
          url: "../../static/bg4.jpg",
          to: "../../article/patrol_the_mountain/patrol_the_mountain",
        },
        {
          title: "藏羚羊的养护",
          url: "../../static/bg5.jpg",
          to: "../../article/conservation_of_antelope/conservation_of_antelope",
        },
        {
          title: "一切罪恶的起源",
          url: "../../static/bg6.jpg",
          to: "../../article/the_origin_of_all_evil/the_origin_of_all_evil",
        },
        {
          title: "高寒植物",
          url: "../../static/bg7.jpg",
          to: "../../article/alpine_plant/alpine_plant",
        },
      ],
    };
  },
  onLoad() {},
  methods: {
    toAbout() {
      uni.navigateTo({
        url: "../about/about",
      });
    },
    toDesc(url) {
      uni.navigateTo({
        url: url,
      });
    },
    toPosition() {
      uni.openLocation({
        latitude: 36.409464,
        longitude: 94.922781,
      });
    },
    setClipboard() {
      uni.setClipboardData({
        data: "09798410618",
        success: function () {
          uni.showToast({
            icon: "success",
            title: "已复制",
            duration: 1000,
          });
        },
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.header-class {
  position: relative;
  top: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #f3f7f9;
  width: 100%;
  height: 45px;
  padding: 10px;
}
.top-img-class {
  height: 25px;
}
.bg-set {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
}
.item-class {
  position: relative;
  margin: 40rpx;
  width: 670rpx;
  height: 400rpx;
  background-color: #1e1e1e;
  border-radius: 10rpx;
  background-size: 100% 100%;
  box-shadow: 2px 2px 6px #2b2b2b;
}
.title-class {
  position: absolute;
  top: 60rpx;
  left: 50rpx;
  color: #fff;
  font-size: 32rpx;
  font-weight: 600;
}
/deep/button {
  margin-top: 30rpx;
  width: 60%;
  font-size: 35rpx !important;
}
</style>
