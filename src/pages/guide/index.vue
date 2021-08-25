<template>
  <view>
    <view>
      <view
        class="fixed-class top-items-class"
        style="z-index: 999; width: 100%; height: 38px"
        ><view @click="changeSet(0)" class="item-class"
          ><image
            :src="x ? '../../static/all-fill.png' : '../../static/all.png'"
            class="top-img-class"
          ></image
          ><text>全部</text></view
        ><view @click="changeSet(1)" class="item-class"
          ><image
            :src="
              y ? '../../static/reserve-fill.png' : '../../static/reserve.png'
            "
            class="top-img-class"
          ></image
          ><text>保护站</text></view
        ><view @click="changeSet(2)" class="item-class"
          ><image
            :src="
              z ? '../../static/scenery-fill.png' : '../../static/scenery.png'
            "
            class="top-img-class"
          ></image
          ><text>景点</text></view
        ></view
      >
      <image src="../../static/north.png" class="fixed-class north-class" />
      <scroll-view
        scroll-x
        scroll-y
        style="position: relative; height: 176.5vw"
        enhanced
        @scroll="dragend"
        :scroll-top="top"
        :scroll-left="left"
      >
        <view
          :style="
            'position: relative;width:' +
            width +
            'vw; height:' +
            width * 1.765 +
            'vw'
          "
        >
          <view
            class="point-class img-1"
            :style="
              'left: 91.4%; top: 49%;width:' +
              41 * scale +
              'rpx;height:' +
              50 * scale +
              'rpx'
            "
            v-show="!y"
            @click="
              this.show = true;
              this.showItem = 0;
            "
          ></view>
          <view
            class="point-class img-2"
            :style="
              'left: 76%; top: 47.3%;width:' +
              128 * scale +
              'rpx;height:' +
              50 * scale +
              'rpx'
            "
            v-show="!y"
            @click="
              this.show = true;
              this.showItem = 1;
            "
          ></view>
          <view
            class="point-class img-3"
            :style="
              'left: 32%; top: 44%;width:' +
              54 * scale +
              'rpx;height:' +
              50 * scale +
              'rpx'
            "
            v-show="!y"
            @click="
              this.show = true;
              this.showItem = 2;
            "
          ></view>
          <view
            class="point-class img-4"
            :style="
              'left: 71.6%; top: 59.5%;width:' +
              45 * scale +
              'rpx;height:' +
              40 * scale +
              'rpx'
            "
            v-show="!y"
            @click="
              this.show = true;
              this.showItem = 3;
            "
          ></view>
          <view
            class="point-class img-5"
            :style="
              'left: 69%; top: 61%;width:' +
              43 * scale +
              'rpx;height:' +
              54 * scale +
              'rpx'
            "
            v-show="z"
            @click="
              this.show = true;
              this.showItem = 4;
            "
          ></view>
          <view
            class="point-class img-6"
            :style="
              'left: 74%; top: 54.5%;width:' +
              36 * scale +
              'rpx;height:' +
              40 * scale +
              'rpx'
            "
            v-show="z"
            @click="
              this.show = true;
              this.showItem = 5;
            "
          ></view>
          <view
            class="point-class img-7"
            :style="
              'left: 91%; top: 30%;width:' +
              62 * scale +
              'rpx;height:' +
              55 * scale +
              'rpx'
            "
            v-show="!y"
            @click="
              this.show = true;
              this.showItem = 6;
            "
          ></view>
          <view
            class="point-class img-8"
            :style="
              'left: 91%; top: 47.2%;width:' +
              65 * scale +
              'rpx;height:' +
              30 * scale +
              'rpx'
            "
            v-show="!y"
            @click="
              this.show = true;
              this.showItem = 7;
            "
          ></view>
          <view
            class="point-class img-9"
            :style="
              'left: 53%; top: 51%;width:' +
              42 * scale +
              'rpx;height:' +
              50 * scale +
              'rpx'
            "
            v-show="z"
            @click="
              this.show = true;
              this.showItem = 8;
            "
          ></view>
          <view
            class="point-class img-11"
            :style="
              'left: 55%; top: 55%;width:' +
              44 * scale +
              'rpx;height:' +
              45 * scale +
              'rpx'
            "
            v-show="!y"
            @click="
              this.show = true;
              this.showItem = 10;
            "
          ></view>
          <view
            class="point-class img-12"
            :style="
              'left: 86%; top: 51.2%;width:' +
              73 * scale +
              'rpx;height:' +
              40 * scale +
              'rpx'
            "
            v-show="!z"
            @click="
              this.show = true;
              this.showItem = 11;
            "
          ></view>
          <view
            class="point-class img-13"
            :style="
              'left: 50.5%; top: 51.5%;width:' +
              77 * scale +
              'rpx;height:' +
              40 * scale +
              'rpx'
            "
            v-show="!z"
            @click="
              this.show = true;
              this.showItem = 12;
            "
          ></view>
          <view
            class="point-class img-14"
            :style="
              'left: 68%; top: 63%;width:' +
              81 * scale +
              'rpx;height:' +
              40 * scale +
              'rpx'
            "
            v-show="!z"
            @click="
              this.show = true;
              this.showItem = 13;
            "
          ></view>
          <view
            class="point-class img-15"
            :style="
              'left: 82%; top: 52.2%;width:' +
              86 * scale +
              'rpx;height:' +
              40 * scale +
              'rpx'
            "
            v-show="!z"
            @click="
              this.show = true;
              this.showItem = 14;
            "
          ></view>
          <view
            class="point-class img-16"
            :style="
              'left: 74.5%; top: 55%;width:' +
              77 * scale +
              'rpx;height:' +
              40 * scale +
              'rpx'
            "
            v-show="!z"
            @click="
              this.show = true;
              this.showItem = 15;
            "
          ></view>
          <image
            src="../../static/amap.jpg"
            style="width: 100%; height: 100%"
            @touchmove="touchmove"
            @touchend="touchend"
          />
        </view>
      </scroll-view>
    </view>
    <u-popup
      v-model="show"
      mode="bottom"
      border-radius="30"
      height="260"
      @close="this.showAudio = false"
    >
      <view class="title-class"> {{ info[showItem].title }} </view>
      <view class="desc-class">{{ info[showItem].desc }}</view>
      <u-button
        :custom-style="btnStyle_1"
        plain
        ripple
        shape="circle"
        @click="this.showAudio = !this.showAudio"
      >
        <img
          src="../../static/mic.png"
          style="width: 64rpx; height: 48rpx"
        />语音解说
      </u-button>
      <u-button
        :custom-style="btnStyle_2"
        plain
        ripple
        shape="circle"
        @click="toDetail"
      >
        <img
          src="../../static/detail.png"
          style="width: 64rpx; height: 48rpx"
        />了解详情
      </u-button>
    </u-popup>
    <view class="audio-class" v-if="showAudio">
      <free-audio :audioId="0" :url="info[showItem].path"></free-audio>
    </view>
    <u-tabbar :list="list"></u-tabbar>
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
      preDis: 0,
      scale: 1,
      left: "0px",
      top: "0px",
      pleft: 0,
      ptop: 0,
      width: 100,
      showAudio: false,
      statue: false,
      x: true,
      y: false,
      z: false,
      show: false,
      showItem: 0,
      info: [
        {
          title: "昆仑山口",
          desc: "青海省海西蒙古族藏族自治州格尔木市109国道附近",
          en: "scene/kunlun_scene/kunlun_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E6%98%86%E4%BB%91%E5%B1%B1.m4a?raw=true",
        },
        {
          title: "杰桑·索南达杰烈士纪念碑",
          desc: "青海省玉树藏族自治州曲麻莱县109国道西100米",
          en: "scene/monument_scene/monument_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E6%9D%B0%E6%A1%91%C2%B7%E7%B4%A2%E5%8D%97%E8%BE%BE%E6%9D%B0%E7%BA%AA%E5%BF%B5%E7%A2%91.m4a?raw=true",
        },
        {
          title: "布喀达坂峰",
          desc: "青海省玉树藏族自治州治多县",
          en: "scene/bukadaban_scene/bukadaban_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E5%B8%83%E5%96%80%E8%BE%BE%E5%9D%82.aac?raw=true",
        },
        {
          title: "青藏线",
          desc: "青海省玉树藏族自治州治多县",
          en: "scene/qingzang_scene/qingzang_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E9%9D%92%E8%97%8F%E5%85%AC%E8%B7%AF.aac?raw=true",
        },
        {
          title: "沱沱河",
          desc: "青海省海西蒙古族藏族自治州格尔木市",
          en: "scene/tuotuo_scene/tuotuo_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E6%B2%B1%E6%B2%B1%E6%B2%B3.aac?raw=true",
        },
        {
          title: "五道梁",
          desc: "青海省玉树藏族自治州治多县",
          en: "scene/wudaoliang_scene/wudaoliang_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E4%BA%94%E9%81%93%E6%A2%81.m4a?raw=true",
        },
        {
          title: "察尔汗盐湖",
          desc: "青海省海西蒙古族藏族自治州格尔木市北60公里",
          en: "scene/chaerhan_scene/chaerhan_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E5%AF%9F%E5%B0%94%E6%B1%97%E7%9B%90%E6%B9%96.m4a?raw=true",
        },
        {
          title: "三江源",
          desc: "青海省海西蒙古族藏族自治州",
          en: "scene/sanjiangyuan_scene/sanjiangyuan_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E4%B8%89%E6%B1%9F%E6%BA%90.m4a?raw=true",
        },
        {
          title: "卓乃湖",
          desc: "青海省玉树藏族自治州治多县",
          en: "scene/zhuonai_scene/zhuonai_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E5%8D%93%E4%B9%83%E6%B9%96.m4a?raw=true",
        },
        {
          title: "尕朵觉沃",
          desc: "青海省玉树藏族自治州称多县尕朵乡",
          en: "scene/gaduojuewo_scene/gaduojuewo_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E5%B0%95%E6%9C%B5%E8%A7%89%E6%B2%83.m4a?raw=true",
        },
        {
          title: "楚玛尔河",
          desc: "青海省玉树藏族自治州西部",
          en: "scene/chumaer_scene/chumaer_scene",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E6%A5%9A%E7%8E%9B%E5%B0%94%E6%B2%B3.m4a?raw=true",
        },
        {
          title: "不冻泉保护站",
          desc: "青海省玉树藏族自治州曲麻莱县109国道北50米",
          en: "station/bdq_station/bdq_station",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E6%BB%95%E7%BB%8D%E6%B3%BD%20%E4%B8%8D%E5%86%BB%E6%B3%89.aac?raw=true",
        },
        {
          title: "卓乃湖保护站",
          desc: "青海省玉树藏族自治州治多县卓乃湖旁",
          en: "station/znh_station/znh_station",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E4%BF%9D%E6%8A%A4%E7%AB%99-%E5%8D%93%E4%B9%83%E6%B9%96%E4%BF%9D%E6%8A%A4%E7%AB%99.m4a?raw=true",
        },
        {
          title: "沱沱河保护站",
          desc: "青海省玉树藏族自治州治多县109国道北50米",
          en: "station/tth_station/tth_station",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E6%B2%B1%E6%B2%B1%E6%B2%B3%E4%BF%9D%E6%8A%A4%E7%AB%991.m4a?raw=true",
        },
        {
          title: "索南达杰保护站",
          desc: "青海省玉树藏族自治州治多县G109(京拉线)",
          en: "station/sndj_station/sndj_station",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E6%9D%B0%E6%A1%91%C2%B7%E7%B4%A2%E5%8D%97%E8%BE%BE%E6%9D%B0%E7%BA%AA%E5%BF%B5%E7%A2%91.m4a?raw=true",
        },
        {
          title: "五道梁保护站",
          desc: "青海省玉树藏族自治州治多县109国道北50米",
          en: "station/wdl_station/wdl_station",
          path: "https://github.com/cjdjczym/trans/blob/main/%E6%99%AF%E5%8C%BA%E9%9F%B3%E9%A2%91%E6%96%87%E4%BB%B6/%E4%BA%94%E9%81%93%E6%A2%81%E4%BF%9D%E6%8A%A4%E7%AB%99.m4a?raw=true",
        },
      ],
      btnStyle_1: {
        position: "absolute",
        left: "100rpx",
        top: "158rpx",
        color: "#2c2c2c",
        height: "75rpx",
        width: "240rpx",
        fontSize: "28rpx",
      },
      btnStyle_2: {
        position: "absolute",
        right: "100rpx",
        top: "158rpx",
        color: "#2c2c2c",
        height: "75rpx",
        width: "240rpx",
        fontSize: "28rpx",
      },
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
  mounted() {},
  watch: {
    showAudio: {
      handler(newVal) {
        if (!newVal) {
          uni.$emit("stop", 0);
        }
      },
    },
  },
  methods: {
    toDetail() {
      uni.navigateTo({
        url: "../../" + this.info[this.showItem].en,
      });
    },
    changeSet(set) {
      let sets = [this.x, this.y, this.z];
      if (!sets[set]) {
        sets = [false, false, false];
        sets[set] = true;
        this.x = sets[0];
        this.y = sets[1];
        this.z = sets[2];
      }
    },
    touchend() {
      this.preDis = 0;
      this.statue = false;
    },
    dragend(e) {
      if (!this.statue) {
        this.pleft =
          (100 * e.detail.scrollLeft) / wx.getSystemInfoSync().windowWidth;
        this.ptop =
          (100 * e.detail.scrollTop) / wx.getSystemInfoSync().windowWidth;
      }
    },
    touchmove(e) {
      if (e.touches[1] != undefined) {
        this.statue = true;
        let xMove = e.touches[1].clientX - e.touches[0].clientX;
        let yMove = e.touches[1].clientY - e.touches[0].clientY;
        let distance = Math.sqrt(xMove * xMove + yMove * yMove);
        if (this.preDis == 0) this.preDis = distance;
        let prescale = this.scale + 0.008 * (distance - this.preDis);
        prescale = prescale > 4 ? 4 : prescale;
        let deltaSize =
          (50 * (prescale - this.scale)) / wx.getSystemInfoSync().windowWidth;
        let preLeft =
          this.pleft +
          (e.touches[1].clientX + e.touches[0].clientX) * deltaSize;
        let preTop =
          this.ptop + (e.touches[1].clientY + e.touches[0].clientY) * deltaSize;
        this.pleft = preLeft < 0 ? 0 : preLeft;
        this.ptop = preTop < 0 ? 0 : preTop;
        this.left =
          (this.pleft * wx.getSystemInfoSync().windowWidth) / 100 + "px";
        this.top =
          (this.ptop * wx.getSystemInfoSync().windowWidth) / 100 + "px";
        this.scale = prescale < 1 ? 1 : prescale;
        this.width = 100 * this.scale;
        this.preDis = distance;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.top-items-class {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba($color: #f3f7f8, $alpha: 0.9);
  color: #51b7ad;
}
.top-img-class {
  margin: 10px;
  width: 18px;
  height: 18px;
}
.fixed-class {
  position: fixed;
  top: 0px;
}
.north-class {
  top: 100rpx;
  right: 30rpx;
  width: 80rpx;
  height: 80rpx;
  z-index: 101;
}
.item-class {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 10px;
}
.title-class {
  position: relative;
  top: 28rpx;
  left: 40rpx;
  font-weight: 700;
  font-size: 40rpx;
  letter-spacing: 4rpx;
  color: #2c2c2c;
}
.desc-class {
  position: relative;
  top: 40rpx;
  left: 40rpx;
  font-size: 24rpx;
  color: #2c2c2c;
}
.point-class {
  z-index: 99;
  position: absolute;
  background-size: 100% 100%;
}
.audio-class {
  position: fixed;
  left: 50%;
  transform: translateX(-50%);
  top: 100rpx;
  z-index: 10076;
}
.img-1 {
  background-image: url("../../static/img1.png");
  z-index: 97;
}
.img-2 {
  background-image: url("../../static/img2.png");
  z-index: 98;
}
.img-3 {
  background-image: url("../../static/img3.png");
}
.img-4 {
  background-image: url("../../static/img4.png");
}
.img-5 {
  background-image: url("../../static/img5.png");
}
.img-6 {
  background-image: url("../../static/img6.png");
}
.img-7 {
  background-image: url("../../static/img7.png");
}
.img-8 {
  background-image: url("../../static/img8.png");
  z-index: 99;
}
.img-9 {
  background-image: url("../../static/img9.png");
}
.img-10 {
  background-image: url("../../static/img10.png");
}
.img-11 {
  background-image: url("../../static/img11.png");
}
.img-12 {
  background-image: url("../../static/img12.png");
  z-index: 96;
}
.img-13 {
  background-image: url("../../static/img13.png");
}
.img-14 {
  background-image: url("../../static/img14.png");
}
.img-15 {
  background-image: url("../../static/img15.png");
  z-index: 95;
}
.img-16 {
  background-image: url("../../static/img16.png");
}
</style>