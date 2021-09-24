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
  </div>
</template>

<script>
export default {
  name: "Carousel",
  data() {
    return {
      index: 0,
      active: 0,
      slides: []
    }
  },
  mounted() {
    this.slides = this.$children.filter(e => e.$options.name === 'Slide')
    this.slides.forEach((slide, i) => {
       slide.index = i;
    })
  },
  computed: {
    slidesCount(){
      return this.slides.length
    }
  },
  methods: {
    next(){
      this.index++;
      if (this.index >= this.slidesCount){
        this.index = 0
      }
    },
    prev(){
      this.index--
      if (this.index < 0){
        this.index = this.slidesCount - 1
      }
    }
  }
}
</script>

<style scoped>

</style>
