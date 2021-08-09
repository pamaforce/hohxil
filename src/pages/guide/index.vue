<template>
  <view>
    <view>
      <view
        class="fixed-class top-items-class"
        style="z-index: 999; width: 100%"
        ><view @click="changeSet(0)" class="item-class"
          ><image
            :src="x ? '../../static/all-fill.png' : '../../static/all.png'"
            class="top-img-class"
          ></image
          ><text :style="x ? 'color: white' : ''">全部</text></view
        ><view @click="changeSet(1)" class="item-class"
          ><image
            :src="
              y ? '../../static/reserve-fill.png' : '../../static/reserve.png'
            "
            class="top-img-class"
          ></image
          ><text :style="y ? 'color: white' : ''">保护站</text></view
        ><view @click="changeSet(2)" class="item-class"
          ><image
            :src="
              z ? '../../static/scenery-fill.png' : '../../static/scenery.png'
            "
            class="top-img-class"
          ></image
          ><text :style="z ? 'color: white' : ''">景点</text></view
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
              'left: 91%; top: 49%;width:' +
              55 * scale +
              'rpx;height:' +
              60 * scale +
              'rpx'
            "
            @click="
              this.show = true;
              this.showItem = 0;
            "
          ></view>
          <view
            class="point-class img-2"
            :style="
              'left: 85%; top: 47.3%;width:' +
              91 * scale +
              'rpx;height:' +
              50 * scale +
              'rpx'
            "
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
            @click="
              this.show = true;
              this.showItem = 2;
            "
          ></view>
          <view
            class="point-class img-4"
            :style="
              'left: 71.8%; top: 58%;width:' +
              45 * scale +
              'rpx;height:' +
              40 * scale +
              'rpx'
            "
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
            @click="
              this.show = true;
              this.showItem = 4;
            "
          ></view>
          <view
            class="point-class img-6"
            :style="
              'left: 72%; top: 54%;width:' +
              78 * scale +
              'rpx;height:' +
              45 * scale +
              'rpx'
            "
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
            @click="
              this.show = true;
              this.showItem = 6;
            "
          ></view>
          <view
            class="point-class img-8"
            :style="
              'left: 94%; top: 46.5%;width:' +
              45 * scale +
              'rpx;height:' +
              50 * scale +
              'rpx'
            "
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
              55 * scale +
              'rpx'
            "
            @click="
              this.show = true;
              this.showItem = 10;
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
      <free-audio :audioId="0" :url="path"></free-audio>
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
      path: "/static/audio/example.mp3",
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
          en: "kunlun_scene",
        },
        {
          title: "杰桑·索南达杰烈士纪念碑",
          desc: "青海省玉树藏族自治州曲麻莱县109国道西100米",
          en: "monument_scene",
        },
        {
          title: "布喀达坂峰",
          desc: "青海省玉树藏族自治州治多县",
          en: "bukadaban_scene",
        },
        {
          title: "青藏线",
          desc: "青海省玉树藏族自治州治多县",
          en: "qingzang_scene",
        },
        {
          title: "沱沱河",
          desc: "青海省海西蒙古族藏族自治州格尔木市",
          en: "tuotuo_scene",
        },
        {
          title: "五道梁保护站",
          desc: "青海省玉树藏族自治州治多县109国道北50米",
          en: "wudaoliang_scene",
        },
        {
          title: "察尔汗盐湖",
          desc: "青海省海西蒙古族藏族自治州格尔木市北60公里",
          en: "chaerhan_scene",
        },
        {
          title: "三江源",
          desc: "青海省海西蒙古族藏族自治州",
          en: "sanjiangyuan_scene",
        },
        {
          title: "卓乃湖",
          desc: "青海省玉树藏族自治州治多县",
          en: "zhuonai_scene",
        },
        {
          title: "尕朵觉沃",
          desc: "青海省玉树藏族自治州称多县尕朵乡",
          en: "gaduojuewo_scene",
        },
        {
          title: "楚玛尔河",
          desc: "青海省玉树藏族自治州西部",
          en: "chumaer_scene",
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
        url: "../scene/" + this.info[this.showItem].en,
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
        console.log(e);
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
  background-color: rgba($color: #000, $alpha: 0.9);
  color: #878787;
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
}
.img-2 {
  background-image: url("../../static/img2.png");
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
</style>