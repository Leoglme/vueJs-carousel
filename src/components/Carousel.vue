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
  props: {
    slides: {type: Number, default: 0}
  },
  data() {
    return {
      index: 0,
      active: 0,
      direction: "right"
    }
  },
  watch: {
    slides(){
      if (this.index >= this.slidesCount) {
        this.index = this.slidesCount - 1
      }
    }
  },
  computed: {
    slidesCount() {
      return this.slides
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
      this.direction = i > this.index ? 'right' : 'left';
      this.index = i
    }
  }
}
</script>

<style scoped>

</style>
