<template>
  <div class="page">
    <Header :loggedIn="loggedIn"/>
    <section class="p_container container">
      <Partnership />
    </section>
  </div>
</template>

<script>
  import Header from '~/components/Header.vue'
  import Partnership from '~/components/Partnership.vue'

  export default {
    components: {
      Header,
        Partnership
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

