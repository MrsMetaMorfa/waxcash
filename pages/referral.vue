<template>
  <div class="page">
    <MobileNavigation :loggedIn="loggedIn" />
    <Header :loggedIn="loggedIn"/>
    <section class="p_container container">
      <Referral />
      <Modals />
    </section>
  </div>
</template>

<script>
  import MobileNavigation from '~/components/MobileNavigation'
  import Header from '~/components/Header'
  import Referral from '~/components/Referral'
  import Modals from '~/components/Modals'

  export default {
    components: {
      Header,
      Referral,
      Modals,
      MobileNavigation
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
    background-image: url('~/assets/images/order-bg.jpg');
    background-size: cover;
    background-position: center;
  }

  @media screen and (max-width: 1824px) {
  }
  @media screen and (max-width: 1146px) {
  }
  @media screen and (max-width: 900px) {
  }
  @media screen and (max-width: 767px) {
  }
  @media screen and (max-width: 631px) {
  }
</style>

