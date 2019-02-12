<template>
  <div class="modals container">
    <Order />
    <Refill />
    <Help />
    <Notification />
  </div>
</template>

<script>
  import Order from '~/components/Order'
  import Refill from '~/components/Refill'
  import Help from '~/components/Help'
  import Notification from '~/components/Notification'

  export default {
      components: {
          Order,
          Refill,
          Help,
          Notification
      }
  }
</script>

<style lang="less">
  .modals {
    width: 100%;
    position: fixed;
    top: 80px;
    left: 0;
    right: 0;
    bottom: 0;
    display: none;
    background: transparent url("~assets/images/order-bg.jpg") no-repeat center top;
    background-size: cover;
    padding: 29px;
    overflow-y: auto;
    z-index: 499;
    justify-content: center;
    align-items: center;
    &.active {
      display: flex;
    }
  }
</style>

