<template lang="pug">
  .insta-post
    insta-header(
      :avatar="avatar"
      :handle="handle"
      :status="status"
    )
    .insta-image(v-show="imgSrc && (!videoSrc || !playing)" :style="{ backgroundImage: 'url(' + imgSrc + ')' }")
    .insta-video(v-show="videoSrc && (playing || !imgSrc)")
      video(v-if="videoSrc" ref="video" loop muted)
        source(:src="videoSrc")
    insta-banner(:likes="likes" @like="like")
</template>

<script>
import InstaHeader from './InstaHeader.vue'
import InstaBanner from './InstaBanner.vue'

export default {
  props: [
    'avatar',
    'handle',
    'status',
    'imgSrc',
    'videoSrc',
    'likes',
    'playing'
  ],
  methods: {
    like () { this.$emit('like') }
  },
  mounted () {
    // Wait for refs to be there
    this.$watch('playing', (playing) => {
      if (this.$refs.video) {
          if (playing) {
            this.$refs.video.currentTime = 0
            this.$refs.video.play()
          } else {
            this.$refs.video.pause()
          }
      }
    }, { immediate: true })
  },
  components: {
    InstaHeader,
    InstaBanner
  }
}
</script>

<style lang="scss">
.insta-post {
  max-width: 600px;
  background-color: #fff;
  border-radius: 3px;
  border: 1px solid #e6e6e6;
  &.responsive {
    @media(max-width: 600px) {
      background-color: inherit;
      border: 0;
    }
  }
}

.insta-image, .insta-video {
  height: 0;
  padding-top: 100%;
  overflow: hidden;
  background-size: cover;
  background-position: center center;
}
.insta-video {
  position: relative;
}
.insta-video video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
