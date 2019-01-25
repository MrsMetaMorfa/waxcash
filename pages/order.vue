<template>
  <div class="page">
    <Header :loggedIn="loggedIn"/>
    <section class="p_container container">
      <Order />
    </section>
  </div>
</template>

<script>
  import Header from '~/components/Header.vue'
  import Order from '~/components/Order.vue'

  export default {
    components: {
      Header,
      Order
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
    background: transparent url("~assets/images/order-bg.jpg") no-repeat center top;
    background-size: cover;
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

