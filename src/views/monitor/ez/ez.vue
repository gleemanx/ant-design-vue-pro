<template>
  <a-card :bordered="false">
    <div id="video-container" style="width:850px;height:500px"></div>
    <a-button :loading="loading" type="primary" @click="play">播放</a-button>
    <a-button :loading="loading" type="primary" @click="pause">暂停</a-button>
    <a-button :loading="loading" type="primary" @click="startSave">开始保存</a-button>
  </a-card>
</template>

<script>
import EZUIKit from 'ezuikit-js'
var player = ''
export default {
    data () {
        return {
        }
    },
    methods: {
        pause () {
            player.stop()
        },
        play () {
            player.play()
        },
        startSave () {
            player.startSave()
        }
    },
    mounted: function () {
        player = new EZUIKit.EZUIKitPlayer({
        id: 'video-container', // 视频容器ID
        width: 750,
        height: 350,
        header: ['zoom'],
        templete: 'standard',
        footer: ['fullScreen', 'hd'],
        accessToken: 'at.9zxpac465xb1y3lyb7kz3qfxalntjawy-5j31ytcjia-1dv1ico-khdsd3gbz',
        url: 'ezopen://QTTOWI@open.ys7.com/F54953128/1.hd.live'
        })
       player.play()
    }
}
</script>

<style>

</style>
