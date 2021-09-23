<template>
  <Carousel>
    <h1>toto</h1>
    <Slide>
       Salut les gens
    </Slide>
    <Slide>
      Aurevoir les gens
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
  }
}
</script>

<style>
</style>
