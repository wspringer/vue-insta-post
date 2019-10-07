<template>
  <div id="app">
    <insta-post
      class="responsive"
      responsive="true"
      avatar="https://scontent.fams1-2.fna.fbcdn.net/v/t1.0-1/p480x480/46216836_10215668229471510_264073753502154752_n.jpg?_nc_cat=101&_nc_oc=AQluFqJgI29pth96CYuNyC-NfzPswSm9Q6IJnAB7PkHoLOzjwAoCAVe8AgYeySL0irQ&_nc_ht=scontent.fams1-2.fna&oh=ddf11ec474b04a980708a2340605d33b&oe=5E35582E"
      handle="dartingtonarts"
      status="Totnes St Mary Church"
      :playing="playing"
      :likes="likes"
      img-src="https://instagram.fams1-2.fna.fbcdn.net/vp/a568e49c0a47941199ce600c60ad5294/5E1B5D1B/t51.2885-15/e35/71319495_1404228989731453_3686260001289200731_n.jpg?_nc_ht=instagram.fams1-2.fna.fbcdn.net&_nc_cat=101"
      video-src="https://cdn.theguardian.tv/webM/2015/07/20/150716YesMen_synd_768k_vp8.webm"
      @like="like"
    />
    <button @click="play">Play</button>
    <button @click="pause">Pause</button>
  </div>
</template>

<script>
import InstaPost from './InstaPost.vue'
import 'focus-visible'

export default {
  name: 'app',
  data () {
    return {
      likes: 3,
      playing: false
    }
  },
  methods: {
    like () {
      this.likes += 1
    },
    play () {
      this.playing = true
    },
    pause () {
      this.playing = false
    }
  },
  components: {
    InstaPost
  }
}
</script>

<style>
body {
  background-color:rgb(250, 250, 250);
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-left: auto;
  margin-right: auto;
  max-width: 600px;
  background-color:rgb(250, 250, 250);
}
.js-focus-visible :focus:not(.focus-visible) {
  outline: none;
}
body {
  margin: 20px 0;
}
</style>

