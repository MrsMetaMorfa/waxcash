<template>
  <div class="page">
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
    </section>
  </div>
</template>

<script>
  import Header from '~/components/Header.vue'
  import AsideBonus from '~/components/AsideBonus.vue'
  import AsideNews from '~/components/AsideNews.vue'
  import WithdrowList from '~/components/WithdrowList.vue'
  import MainLeft from '~/components/MainLeft.vue'
  import MainRight from '~/components/MainRight.vue'

  export default {
    components: {
      Header,
      AsideBonus,
      AsideNews,
      WithdrowList,
      MainLeft,
      MainRight
    },
    data() {
      return {
        loggedIn: true,
        loggedFirst: true
      }
    },
    methods: {}
  }
</script>

<style lang="less">
  .p_container {
    margin-top: 80px;
    min-height: calc(100vh - 80px);
    padding: 14px;
  }
  .content_left {
    width: calc(100% - 294px);
  }
  .content_right {
    width: 280px;
    margin-left: 14px;
  }
  .p_main {
    margin-top: 14px;
  }

  @media screen and (max-width: 1499px) {
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
  @media screen and (max-width: 1072px) {
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


