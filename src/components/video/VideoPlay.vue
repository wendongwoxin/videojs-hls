<template>
    <video id="my-video" class="video-js vjs-default-skin" controls preload="auto" :style="{width:this.width,height:this.height}">
        <source :src="hlsSource" type="application/x-mpegURL">
    </video>
</template>
<script>
import videojs from 'video.js'
import 'videojs-contrib-hls'
export default {
    name: 'VideoPlay',
    props: {
        options: Object,
        hlsSource: String,
        width: String,
        height: String
    },
    data () {
        return {
            player: null
        }
    },
    mounted () {
        this.player =videojs('my-video', this.options)
    },
    methods: {
        play () {
            this.player.play()
        }
    }
}
</script>