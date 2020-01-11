<template>
  <div id="app">
    <Header :seller="seller"/>
  </div>
</template>

<script>
  import Header from 'components/header'
  import { getSeller } from 'api'

  export default {
    name: 'app',
    components: {
      Header
    },
    data () {
      return {
        seller: {}
      }
    },
    created () {
      this._getSeller()
    },
    methods: {
      _getSeller () {
        getSeller().then(seller => {
          this.seller = seller
        })
      }
    }
  }
</script>

<style lang="stylus" scoped>

</style>
