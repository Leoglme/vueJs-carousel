<template>
  <Carousel>
    <Slide>
       Slide 1
    </Slide>
    <Slide>
      Slide 2
    </Slide>
    <Slide>
      Slide 3
    </Slide>
  </Carousel>
</template>

<script>
import Carousel from "@/components/Carousel";
import Slide from "@/components/Slide";
export default {
  name: 'App',
  components: {
    Carousel, Slide
  },
}
</script>

<style>
</style>
