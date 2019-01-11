<template>
  <section class="p_container container container--justify">
    <div class="content_left">
      <WithdrowList/>
      <div class="p_main container container--justify">
        <MainLeft/>
        <MainRight/>
      </div>
    </div>
    <aside class="content_right">
      <AsideBonus/>
      <AsideNews/>
    </aside>
  </section>
</template>

<script>
  import AppLogo from '~/components/AppLogo.vue'
  import AsideBonus from '~/components/AsideBonus.vue'
  import AsideNews from '~/components/AsideNews.vue'
  import WithdrowList from '~/components/WithdrowList.vue'
  import MainLeft from '~/components/MainLeft.vue'
  import MainRight from '~/components/MainRight.vue'

  export default {
    components: {
      AppLogo,
      AsideBonus,
      AsideNews,
      WithdrowList,
      MainLeft,
      MainRight
    }
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
</style>

