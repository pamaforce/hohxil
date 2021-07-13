<template>
  <view>
    <view class="u-text-center">主页暂未开发</view>
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
    };
  },
  onLoad() {},
  methods: {},
};
</script>

<style lang="scss">
</style>
