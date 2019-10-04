<template lang="pug">
  .insta-post
    insta-header(
      :avatar="avatar"
      :handle="handle"
      :status="status"
    )
    .insta-image(v-if="imgSrc" :style="{ backgroundImage: 'url(' + imgSrc + ')' }")
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
    'likes'
  ],
  methods: {
    like () { this.$emit('like') }
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

.insta-image {
  height: 0;
  padding-top: 100%;
  overflow: hidden;
  background-size: cover;
  background-position: center center;
}
</style>
