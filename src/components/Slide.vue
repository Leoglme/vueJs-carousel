<template>
  <transition :name="transition">
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
    },
    transition(){
      const direction = this.$parent.direction;
      if (direction){
        return 'slide-' + direction
      }
      return direction;
    }
  }
}
</script>

<style src="../CSS/carousel-anim.css">

</style>
