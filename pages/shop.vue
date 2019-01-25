<template>
  <div class="page">
    <Header :loggedIn="loggedIn"/>
    <div class="p_container">
      <div class="p_main container container--justify">
        <ShopLeft :loggedIn="loggedIn" :loggedFirst="loggedFirst"/>
        <ShopRight/>
      </div>
    </div>
  </div>
</template>

<script>
  import Header from '~/components/Header.vue'
  import ShopLeft from '~/components/ShopLeft'
  import ShopRight from '~/components/ShopRight'

  export default {
    components: {
      Header,
      ShopLeft,
      ShopRight,
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
    margin-top: 80px;
    height: calc(100vh - 80px);
    padding: 14px;
    .p_main {
      height: 100%;
    }
  }
  @media screen and (max-width: 1146px) {
      .p_container {
          height: auto;
      }
    .p_main {
      flex-wrap: wrap;
        height:  auto!important;
    }
  }
  @media screen and (max-width: 767px) {
    .p_container {
      margin-top: 132px;
    }
  }
  @media screen and (max-width: 631px) {
    .p_container {
      margin-top: 0;
    }
  }

</style>

