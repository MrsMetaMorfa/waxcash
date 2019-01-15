<template>
  <vue-scroll class="withdraw" :ops="opsVertical">
    <ul class="container">
      <li class="withdraw_lvl-1 qiwi">
        <div class="container">
          <div class="image"><img src="~assets/images/avatar_1.jpg" alt="Avatar"></div>
          <p>
            <span class="name">Seized</span><br>
            <span class="price">412.98 Р</span>
          </p>
        </div>
      </li>
      <li class="withdraw_lvl-1 qiwi">
        <div class="container">
          <div class="image"><img src="~assets/images/avatar_1.jpg" alt="Avatar"></div>
          <p>
            <span class="name">Seized</span><br>
            <span class="price">412.98 Р</span>
          </p>
        </div>
      </li>
      <li class="withdraw_lvl-2 qiwi">
        <div class="container">
          <div class="image"><img src="~assets/images/avatar_1.jpg" alt="Avatar"></div>
          <p>
            <span class="name">Seized</span><br>
            <span class="price">412.98 Р</span>
          </p>
        </div>
      </li>
      <li class="withdraw_lvl-1 qiwi">
        <div class="container">
          <div class="image"><img src="~assets/images/avatar_1.jpg" alt="Avatar"></div>
          <p>
            <span class="name">Seized</span><br>
            <span class="price">412.98 Р</span>
          </p>
        </div>
      </li>
      <li class="withdraw_lvl-1 qiwi">
        <div class="container">
          <div class="image"><img src="~assets/images/avatar_1.jpg" alt="Avatar"></div>
          <p>
            <span class="name">Seized</span><br>
            <span class="price">412.98 Р</span>
          </p>
        </div>
      </li>
      <li class="withdraw_lvl-1 qiwi">
        <div class="container">
          <div class="image"><img src="~assets/images/avatar_1.jpg" alt="Avatar"></div>
          <p>
            <span class="name">Seized</span><br>
            <span class="price">412.98 Р</span>
          </p>
        </div>
      </li>
      <li class="withdraw_lvl-1 qiwi">
        <div class="container">
          <div class="image"><img src="~assets/images/avatar_1.jpg" alt="Avatar"></div>
          <p>
            <span class="name">Seized</span><br>
            <span class="price">412.98 Р</span>
          </p>
        </div>
      </li>
      <li class="withdraw_lvl-3 visa">
        <div class="container">
          <div class="image"><img src="~assets/images/avatar_1.jpg" alt="Avatar"></div>
          <p>
            <span class="name">Seized</span><br>
            <span class="price">412.98 Р</span>
          </p>
        </div>
      </li>
      <li class="withdraw_lvl-1 qiwi">
        <div class="container">
          <div class="image"><img src="~assets/images/avatar_1.jpg" alt="Avatar"></div>
          <p>
            <span class="name">Seized</span><br>
            <span class="price">412.98 Р</span>
          </p>
        </div>
      </li>
    </ul>
  </vue-scroll>
</template>

<script>
    export default {
        data() {
            return {
                opsVertical: {
                    vuescroll: {
                        mode: 'native',
                        zooming: false
                    },
                    scrollPanel: {
                        scrollingY: false
                    },
                    rail: {
                        background: '#21222e',
                        opacity: 1,
                        size: '5px'
                    },
                    bar: {
                        background: 'linear-gradient(to right, #2af598, #08afe9)',
                        size: '5px',
                        keepShow: true
                    }
                }
            }
        }
    }
</script>

<style lang="less">
  .withdraw {
    background-color: rgb(22, 23, 31);
    width: 100%;
    overflow-x: hidden;
    height: 71px!important;
    &.__vuescroll .__rail-is-horizontal {
      bottom: 0!important;
    }
    &.__vuescroll .__panel.__native{
      height: calc(100% + 17px);
      margin-bottom: -17px;
      padding-bottom: 17px;
      .container {
        padding-bottom: 5px;
      }
    }
    ul {
      padding: 0;
      list-style-type: none;
      li {
        width: 12.5%;
        min-width: 150px;
        display: flex;
        &:before {
          content: '';
          display: block;
          width: 5px;
          height: 100%;
          background: #80d0c7 linear-gradient(transparent, #0093e9);
          background-size: 100%;
        }
        .container {
          width: calc(100% - 5px);
          align-items: center;
          justify-content: center;
          padding: 10px;
          .image {
            border-radius: 50%;
            box-shadow: 0px 9px 7px 0px rgba(0, 0, 0, 0.2);
            width: 46px;
            height: 46px;
            padding: 4px;
            background: #80d0c7 linear-gradient(-128deg, transparent, #0093e9);
            img {
              display: block;
              width: 38px;
              height: 38px;
              border-radius: 50%;
            }
          }
          p {
            font-size: 14px;
            margin-left: 10px;
            .price {
              color: #5499e8;
              font-size: 16px;
            }
          }
        }

        &.withdraw_lvl-1 {
          background: #272938 url("~assets/images/withdrawal-bg.jpg") no-repeat center;
          background-size: cover;
        }
        &.withdraw_lvl-2 {
          background: #272938 url("~assets/images/withdrawal-bg-lvl2.jpg") no-repeat center;
          background-size: cover;
          &:before {
            background: #00dbde linear-gradient(transparent, #fc00ff);
          }
          .image {
            background: #00dbde linear-gradient(-128deg, transparent, #fc00ff);
          }
        }
        &.withdraw_lvl-3 {
          background: #272938 url("~assets/images/withdrawal-bg-lvl3.jpg") no-repeat center;
          background-size: cover;
          &:before {
            background: #ffe53b linear-gradient(transparent, #ff2525);
          }
          .image {
            background: #ffe53b linear-gradient(-128deg, transparent, #ff2525);
          }
          p .price {
            color: #ffac35!important;
          }
        }
        &.qiwi {
          &.withdraw_lvl-1 .container {
            background: transparent url("~assets/images/withdrawal-qiwi.png");
            background-size: cover;
          }
          &.withdraw_lvl-2 .container, &.withdraw_lvl-3 .container {
            background: transparent url("~assets/images/withdrawal-qiwi-full.png");
            background-size: cover;
          }
        }
        &.visa {
          /*&.withdraw_lvl-1 .container {*/
          /*background: transparent url("~assets/images/withdrawal-visa.png");*/
          /*background-size: cover;*/
          /*}*/
          &.withdraw_lvl-2 .container, &.withdraw_lvl-3 .container {
            background: transparent url("~assets/images/withdrawal-visa-full.png");
            background-size: cover;
          }
        }
      }
    }
  }
</style>

