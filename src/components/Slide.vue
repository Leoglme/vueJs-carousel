<template>
  <div v-show="visible">
    Index: {{index}}
    <slot/>
  </div>
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

<style scoped>

</style>
