<template lang="pug">
  .insta-banner
    button: span.sprite-heart(@click="like")
    button: span.sprite-speak
    button: span.sprite-export
    button: span.sprite-bookmark
    .insta-likes(v-if="likes") {{likes}} vind-ik-leuks
</template>

<script>
export default {
  props: [ 'likes' ],
  methods: {
    like () { this.$emit('like') }
  }
}
</script>

<style lang="scss">
  .insta-banner {
    display: grid;
    grid-template-columns: 40px 40px auto 40px;
    grid-template-rows: 1fr 1fr;
    padding: 0 8px 0 8px;
    text-align: left;
  }
  button {
    height: 40px;
    width: 40px;
    background: 0 0;
    border: 0;
    cursor: pointer;
  }
  .sprite-heart, .sprite-speak, .sprite-export, .sprite-bookmark {
    display: inline-block;
    background-image: url('../assets/sprites.png');
    background-size: 355px 344px;
    width: 24px;
    height: 24px;
  }
  .sprite-heart {
    background-position: -75px -295px;
  }
  .sprite-speak {
    background-position: -177px -197px;
  }
  .sprite-export {
    background-position: -331px -225px;
  }
  .sprite-bookmark {
    background-position: -250px -320px;
  }
  .insta-likes {
    grid-column: 1/5;
    font-weight: 600;
    font-size: 14px;
    line-height: 18px;
    padding: 0 8px;
  }
</style>

