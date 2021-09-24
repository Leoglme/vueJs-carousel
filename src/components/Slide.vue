<template>
  <transition :name="transition">
    <div v-show="visible">
      <slot/>
    </div>
  </transition>
</template>

<script>
export default {
  name: "Slide",
  props: {
    index: {type: Number, default: 0}
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
