<template>
  <div class="page">
    <MobileNavigation :loggedIn="loggedIn" />
    <Header :loggedIn="loggedIn"/>
    <section class="p_container container container--justify">
      <div class="content_left">
        <WithdrowList/>
        <div class="p_main container container--justify">
          <MainLeft :loggedIn="loggedIn" :loggedFirst="loggedFirst"/>
          <MainRight/>
        </div>
      </div>
      <aside class="content_right">
        <AsideBonus/>
        <AsideNews/>
      </aside>

      <Modals />
    </section>
  </div>
</template>

<script>
  import MobileNavigation from '~/components/MobileNavigation'
  import Header from '~/components/Header'
  import AsideBonus from '~/components/AsideBonus'
  import AsideNews from '~/components/AsideNews'
  import WithdrowList from '~/components/WithdrowList'
  import MainLeft from '~/components/MainLeft'
  import MainRight from '~/components/MainRight'
  import Modals from '~/components/Modals'

  export default {
    components: {
      MobileNavigation,
      Header,
      AsideBonus,
      AsideNews,
      WithdrowList,
      MainLeft,
      MainRight,
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
  .content_left {
    width: calc(85% - 14px);
  }
  .content_right {
    width: 15%;
    min-width: 280px;
    margin-left: 14px;
  }
  .p_main {
    margin-top: 14px;
    height: calc(100% - 85px);
  }

  @media screen and (max-width: 1824px) {
    .p_container {
      flex-direction: column;
      .content_left {
        width: 100%;
        margin-bottom: 14px;
      }
      .content_right {
        width: 100%;
        display: flex;
        justify-content: center;
        margin: 0;
      }
    }
  }
  @media screen and (max-width: 1146px) {
    .p_main {
      flex-direction: column;
    }
  }
  @media screen and (max-width: 900px) {
    .content_right {
      flex-direction: column;
    }
  }
  @media screen and (max-width: 767px) {
  }
  @media screen and (max-width: 631px) {
  }
</style>

