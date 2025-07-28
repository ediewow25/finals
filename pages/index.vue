<template>
  <v-container fluid>
    <h1 class="text-center mb-6">Video JS</h1>

    <v-row justify="center" align="center">

      <v-col cols="12" md="4">
        <video
          ref="video1"
          class="video-js vjs-default-skin"
          controls
          preload="auto"
          width="350"
          height="240"
        >
          <source src="https://vjs.zencdn.net/v/oceans.mp4" type="video/mp4" />
        </video>
      </v-col>

 
      <v-col cols="12" md="4">
        <video
          ref="video2"
          class="video-js vjs-default-skin"
          controls
          preload="auto"
          width="350"
          height="240"
        >
          <source src="https://test-videos.co.uk/vids/bigbuckbunny/mp4/h264/720/Big_Buck_Bunny_720_10s_1MB.mp4" type="video/mp4" />
        </video>
      </v-col>

  
      <v-col cols="12" md="4">
        <video
          ref="video3"
          class="video-js vjs-default-skin"
          controls
          preload="auto"
          width="350%"
          height="240"
        >
          <source src="https://media.w3.org/2010/05/sintel/trailer.mp4" type="video/mp4" />
        </video>
      </v-col>
    </v-row>
  </v-container>
</template>



<script>
import videojs from 'video.js'
import 'video.js/dist/video-js.css'

export default {
  mounted() {
    this.players = [
      videojs(this.$refs.video1),
      videojs(this.$refs.video2),
      videojs(this.$refs.video3)
    ]
  },
  beforeDestroy() {
    this.players.forEach(player => {
      if (player) player.dispose()
    })
  }
}
</script>

