<template>
  <i class="mdi" v-bind:class="'mdi-' + icon">
  </i>
</template>

<style scoped lang="stylus">
.mdi {
  font-size: 1.3em;
}
</style>

<script>
  export default {
    props: ['icon']
  }
</script>
