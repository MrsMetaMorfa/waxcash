<template>
  <div class="page">
    <MobileNavigation :loggedIn="loggedIn" />
    <Header :loggedIn="loggedIn"/>
    <div class="p_container">
      <div class="p_main container container--justify">
        <ShopLeft :loggedIn="loggedIn" :loggedFirst="loggedFirst"/>
        <ShopRight/>
      </div>

      <Modals />
    </div>
  </div>
</template>

<script>
  import MobileNavigation from '~/components/MobileNavigation.vue'
  import Header from '~/components/Header.vue'
  import ShopLeft from '~/components/ShopLeft'
  import ShopRight from '~/components/ShopRight'
  import Modals from '~/components/Modals'

  export default {
    components: {
      MobileNavigation,
      Header,
      ShopLeft,
      ShopRight,
      Modals
    },
    data() {
      return {
        loggedIn: true,
        loggedFirst: false
      }
    },
    methods: {}
  }
</script>

<style lang="less">
  .p_container {
    padding: 14px;
    .p_main {
      height: 100%;
    }
  }
  @media screen and (max-width: 1146px) {
    .p_main {
      flex-wrap: wrap;
      height:  auto!important;
    }
  }
  @media screen and (max-width: 767px) {
  }
  @media screen and (max-width: 631px) {
  }

</style>

