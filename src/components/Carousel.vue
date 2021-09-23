<template>
   <div>
     <slot/>
   </div>
</template>

<script>
export default {
  name: "Carousel",
  data() {
    return {
      index: 0,
      slides: []
    }
  },
  mounted() {
    this.slides = this.$refs
    this.slides.forEach((slide, i) => {
       slide.index = i;
    })
  }
}
</script>

<style scoped>

</style>
