<template>
  <div id="app">
    <insta-post
      avatar="https://scontent.fams1-2.fna.fbcdn.net/v/t1.0-1/p480x480/46216836_10215668229471510_264073753502154752_n.jpg?_nc_cat=101&_nc_oc=AQluFqJgI29pth96CYuNyC-NfzPswSm9Q6IJnAB7PkHoLOzjwAoCAVe8AgYeySL0irQ&_nc_ht=scontent.fams1-2.fna&oh=ddf11ec474b04a980708a2340605d33b&oe=5E35582E"
      handle="dartingtonarts"
      status="Totnes St Mary Church"
      :likes="likes"
      img-src="https://instagram.fams1-2.fna.fbcdn.net/vp/b22f417ad1bdb0d08f937851b555c4d2/5E3D205F/t51.2885-15/e35/51545982_829939757341825_7408881662271874792_n.jpg?_nc_ht=instagram.fams1-2.fna.fbcdn.net&_nc_cat=101"
      @like="like"
    />
  </div>
</template>

<script>
import InstaPost from './InstaPost.vue'
import 'focus-visible'

export default {
  name: 'app',
  data () {
    return {
      likes: 3
    }
  },
  methods: {
    like () {
      this.likes += 1
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
</style>

