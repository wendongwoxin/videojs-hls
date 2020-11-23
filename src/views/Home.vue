<template>
  <div class="home">
    <VideoPlay class="video" :options="playOptions" :hlsSource="hlsSource" ref="videoplay" width="1080px" height="720px"/>
    <el-button class='btn' type="primary" @click="play">播放</el-button>
  </div>
</template>

<script>
// @ is an alias to /src
import VideoPlay from '@/components/video/VideoPlay'

export default {
  name: 'Home',
  components: {
    VideoPlay
  },
  data () {
    return {
      playOptions: {
        bigPlayButton: false,
        textTrackDisplay: false,
        posterImage: true,
        errorDisplay: false,
        controlBar: true
      },
      hlsSource: 'http://ivi.bupt.edu.cn/hls/cctv1hd.m3u8'
    }
  },
  mounted () {
    this.$nextTick(() => {
      // this.$refs.videoplay.play() 
      // play() failed because the user didn't interact with the document first  【用户没有先去跟网页做交互再执行音频播放】
    })
  },
  methods: {
    play () {
      this.$refs.videoplay.play()
    }
  }
}
</script>

<style scoped lang="scss">
.home {
  text-align: center;
  .video {
    margin: 10px auto;
  }
}
</style>