<template>
  <div id="app">
    <Header :seller="seller"/>
  </div>
</template>

<script>
  import Header from 'components/header'

  export default {
    name: 'app',
    components: {
      Header
    },
    data() {
      return {
        seller: {}
      }
    },
    created() {
    }
  }
</script>

<style lang="stylus" scoped>

</style>
