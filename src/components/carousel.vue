<template lang="jade">
#carousel
  ul
    li(v-for="car in cars")
      .item(v-show="car.show")
        img(:src="images[$index].img")
  button#prev(@click="previous") Previous
  button#next(@click="next") Next
</template>

<script>
export default {
  data () {
    return {
      images: [
        {img: '../static/11.jpg'},
        {img: '../static/22.jpg'},
        {img: '../static/33.jpg'}
      ],
      cars: [
        {show: true},
        {show: false},
        {show: false}
      ]
    }
  },
  methods: {
    previous () {
      this.cars.push(this.cars.shift())
    },
    next () {
      this.cars.unshift(this.cars.pop())
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
</style>
