<template>
  <div class="page">
    <MobileNavigation :loggedIn="loggedIn" />
    <Header :loggedIn="loggedIn"/>
    <section class="p_container container">
      <FAQ />
      <Modals />
    </section>
  </div>
</template>

<script>
  import MobileNavigation from '~/components/MobileNavigation'
  import Header from '~/components/Header'
  import FAQ from '~/components/FAQ'
  import Modals from '~/components/Modals'

  export default {
    components: {
      MobileNavigation,
      Header,
      FAQ,
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

