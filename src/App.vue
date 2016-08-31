<template lang="jade">
#app
  carousel(:dots="dots", :auto-play="autoPlay", :speed="speed", :images="images", :start-at="startAt")
</template>

<script>
import carousel from './components/carousel'

export default {
  data () {
    return {
      dots: true,
      autoPlay: true,
      speed: 3000,
      images: [
        {img: '/static/slider1.jpg'},
        {img: '/static/slider2.jpg'},
        {img: '/static/slider3.jpg'}
      ],
      startAt: 0
    }
  },
  components: {
    carousel
  }
}
</script>

<style src="normalize.css/normalize.css"></style>
