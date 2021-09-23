<template>
  <div>
    Index: {{index}}
    <slot/>
  </div>
</template>

<script>
export default {
  name: "Slide",
  data() {
    console.log(this.$parent.index);
    return {
      index: 0
    }
  },
  computed: {
    visible(){
      return null
    }
  }
}
</script>

<style scoped>

</style>
