<template>
  <div id="app">
    <Header :seller="seller"/>
    <div class="tab-wrapper">
      <Tab :tabs="tabs"/>
    </div>
  </div>
</template>

<script>
  import Header from 'components/header'
  import { getSeller } from 'api'
  import Tab from './components/tab/Tab'
  import Goods from 'components/goods'
  import Ratings from 'components/ratings'
  import Seller from 'components/seller'

  export default {
    name: 'app',
    components: {
      Tab,
      Header
    },
    data () {
      return {
        seller: {}
      }
    },
    computed: {
      tabs () {
        return [
          { label: '商品', component: Goods, data: { seller: this.seller } },
          { label: '评价', component: Ratings, data: { seller: this.seller } },
          { label: '商家', component: Seller, data: { seller: this.seller } }
        ]
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
  .tab-wrapper
    position fixed
    top 136px
    left 0
    right 0
    bottom 0
</style>
