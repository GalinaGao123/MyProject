<template lang="jade">
#carousel
  ul
    li(v-for="car in cars")
      .item(v-show="$index==current", transition="fade")
        img(:src="car.img")
  button#prev(@click="previous") Previous
  button#next(@click="next") Next
</template>

<script>
export default {
  data () {
    return {
      cars: [
        {img: '../static/11.jpg'},
        {img: '../static/22.jpg'},
        {img: '../static/33.jpg'}
      ],
      current: 0
    }
  },
  methods: {
    previous () {
      if (this.current === 0) {
        this.current = 2
      } else {
        this.current--
      }
    },
    next () {
      if (this.current === 2) {
        this.current = 0
      } else {
        this.current++
      }
    }
  }
}
</script>

<style lang="stylus">
#carousel
  width 480px
  overflow hidden
ul
  list-style none
  padding-left 0
  width 300%
  &:after
    content ''
    display table
    clear both
  li
    float left
    width 480px
.fade-transition
  transition all 0.5s ease
  opacity 1
.fade-enter
.fade-leave
  opacity 0
</style>
