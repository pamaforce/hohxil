## 参数

| url      | activeColor | startPic       | endPic         | 组件id                                                |
| -------- | ----------- | -------------- | -------------- | ----------------------------------------------------- |
| 音频链接 | 进度条颜色  | 开始播放的图片 | 暂停播放的图片 | audioId(必填，且id不可为数字0，建议格式 ‘audio’+数字) |

## 使用方法

```javascript
//html
<template>
  <free-audio startPic='/static/images/icon/play.png' endPic='/static/images/icon/stop.png' :audioId='audio1' :url='path'></free-audio>
</template>

//js

import freeAudio from '@/components/free-audio.vue'
export default {
    components: {freeAudio},
    data() {
        return{
            path: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-hello-uniapp/2cc220e0-c27a-11ea-9dfb-6da8e309e0d8.mp3'
        }
    },
    methods: {

    },
} 

//暂停所有音频（一般用于页面切换时停止正在播放的音频）
onUnload() { //普通页面在 onUnload 生命周期中执行
  uni.$emit('stop')
},
onHide() { //tabBar页面在onHide生命周期中执行
  uni.$emit('stop')
}




```

