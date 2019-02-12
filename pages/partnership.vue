<template>
  <div class="page">
    <MobileNavigation :loggedIn="loggedIn" />
    <Header :loggedIn="loggedIn"/>
    <section class="p_container container">
      <Partnership />
      <Modals />
    </section>
  </div>
</template>

<script>
  import MobileNavigation from '~/components/MobileNavigation'
  import Header from '~/components/Header'
  import Partnership from '~/components/Partnership'
  import Modals from '~/components/Modals'

  export default {
    components: {
      MobileNavigation,
      Header,
      Partnership,
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

