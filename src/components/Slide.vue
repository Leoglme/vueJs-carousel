<template>
  <transition name="slide-right">
    <div v-show="visible">
      Index: {{index}}
      <slot/>
    </div>
  </transition>
</template>

<script>
export default {
  name: "Slide",
  data() {
    return {
      index: 0
    }
  },
  computed: {
    visible(){
      return this.index === this.$parent.index
    }
  }
}
</script>

<style src="../CSS/carousel-anim.css">

</style>
