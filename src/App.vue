<template>
  <v-app>
    <div class="center">
      <Carousel :slides="slides - 1">
        <Slide v-for="n in slides" :key="n" :index="n - 1">
          <div class="slide__text">
            slide {{ n }}
          </div>
          <img :src="'https://picsum.photos/id/' + n + '/630/300'" width="100%"/>
        </Slide>
      </Carousel>
      <div style="display: flex">
        <v-btn color="primary" class="mt-5 mr-5" @click="addSlide">Ajouter un slide</v-btn>
        <v-btn color="primary" class="mt-5" @click="removeSlide">Supprimer un slide</v-btn>
      </div>

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
  data() {
    return {
      slides: 5,
    }
  },
  methods: {
    addSlide(){
      this.slides++
    },
    removeSlide(){
      if (this.slides - 1 !== 1){
        this.slides--
      }
    }
  }
};
</script>

<style src="./CSS/carousel.css">

</style>
