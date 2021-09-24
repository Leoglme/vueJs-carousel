<template>
<!--  <v-btn-->
<!--      color="accent"-->
<!--      elevation="2">-->
<!--    coucou-->
<!--  </v-btn>-->
  <v-app>
    <div class="center">
        <Carousel>
          <Slide>
            <div class="slide__text">
              slide 1
            </div>
            <img src="https://picsum.photos/id/1/630/300" width="100%"/>
          </Slide>
          <Slide>
            <div class="slide__text">
              Slide 2
            </div>
            <img src="https://picsum.photos/id/2/630/300" width="100%"/>
          </Slide>
          <Slide>
            <div class="slide__text">
              Slide 3
            </div>
            <img src="https://picsum.photos/id/3/630/300" width="100%"/>
          </Slide>
        </Carousel>
      </div>
  </v-app>
</template>

<script>
import Carousel from "./components/Carousel"
import Slide from "./components/Slide"

export default {
  name: 'App',

  components: {
    Carousel, Slide
  },

  data: () => ({
  }),
};
</script>

<style src="./CSS/carousel.css">

</style>
