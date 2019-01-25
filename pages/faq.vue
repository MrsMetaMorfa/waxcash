<template>
  <div class="page">
    <Header :loggedIn="loggedIn"/>
    <section class="p_container container">
      <FAQ />
    </section>
  </div>
</template>

<script>
  import Header from '~/components/Header.vue'
  import FAQ from '~/components/FAQ.vue'

  export default {
    components: {
      Header,
      FAQ
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

