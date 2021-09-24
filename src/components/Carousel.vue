<template>
  <div class="carousel">
    <slot/>
    <v-btn
        class="carousel__nav carousel__next"
        fab
        small
        @click.prevent="next"
        color="primary">
      <v-icon dark>
        mdi-chevron-right
      </v-icon>
    </v-btn>
    <v-btn
        class="carousel__nav carousel__prev"
        fab
        small
        @click.prevent="prev"
        color="primary">
      <v-icon dark>
        mdi-chevron-left
      </v-icon>
    </v-btn>
    <div class="carousel__pagination">
      <button
          v-for="n in slidesCount"
          :key="n" @click="goTo(n-1)"
          :class="{active: n-1 === index}"/>
    </div>
  </div>
</template>

<script>
export default {
  name: "Carousel",
  data() {
    return {
      index: 0,
      active: 0,
      slides: [],
      direction: null
    }
  },
  mounted() {
    this.slides = this.$children.filter(e => e.$options.name === 'Slide')
    this.slides.forEach((slide, i) => {
      slide.index = i;
    })
  },
  computed: {
    slidesCount() {
      return this.slides.length
    }
  },
  methods: {
    next() {
      this.index++;
      if (this.index >= this.slidesCount) {
        this.index = 0
      }
      this.direction = 'right'
    },
    prev() {
      this.index--
      if (this.index < 0) {
        this.index = this.slidesCount - 1
      }
      this.direction = 'left'
    },
    goTo(i){

      if (i > this.index){
        this.direction = 'right'
      }else {
        this.direction = 'left'
      }
      this.index = i
    }
  }
}
</script>

<style scoped>

</style>
