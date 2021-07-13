<template>
  <view>
    <view>
      <view class="u-absolute top-items-class" style="z-index: 999; width: 100%"
        ><image src="../../static/reserve.png" class="top-img-class"></image
        ><text>保护区</text><view style="width: 20px"></view
        ><image src="../../static/scenery.png" class="top-img-class"></image
        ><text>景点</text></view
      >
      <map
        style="width: 100%; height: 100vh"
        :latitude="latitude"
        :longitude="longitude"
        scale="11"
      >
      </map
    ></view>
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
      id: 0,
      latitude: 35.518996,
      longitude: 93.912953,
    };
  },
  onLoad() {},
  methods: {},
};
</script>

<style lang="scss">
.top-items-class {
  display: flex;
  align-items: center;
  justify-content: center;
}
.top-img-class {
  margin: 10px;
  width: 24px;
  height: 24px;
}
</style>
