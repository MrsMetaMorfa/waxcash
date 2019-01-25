<template>
  <aside class="block p_shop-right">
    <div class="shop_header container container--justify">
      <h2 class="shop_title">
        <img src="~/assets/icons/cart.svg" alt="">
        Корзина
      </h2>
      <p class="shop_total">
        Общая стоимость:
        <span>$534.65</span>
      </p>
    </div>
    <div class="shop_body container">
      <vue-scroll :ops="ops">
        <div class="container shop_container">
          <div class="shop_card container">
            <div class="image">
              <img src="~assets/images/skin1.png" alt="">
            </div>
            <div class="shop_card__inner container container--justify">
              <div class="shop_card__left container">
                <div class="description">
                  <h3>WAX Key</h3>
                  <p>Wax items</p>
                </div>
                <div class="quantity">
                  <button class="btn btn-more" type="button" aria-label="Больше"
                          onclick="var i = this.parentNode.querySelector('.quantity_total').innerHTML;
                          i++; this.parentNode.querySelector('.quantity_total').innerHTML = i;">
                    <span></span></button>
                  <span class="quantity_total">1</span>
                  <button class="btn btn-less" type="button" aria-label="Меньше"
                          onclick="var i = this.parentNode.querySelector('.quantity_total').innerHTML;
                          if (i > 1) {i--; this.parentNode.querySelector('.quantity_total').innerHTML = i;}"><span></span></button>
                </div>
              </div>
              <div class="shop_card__right">
                <p class="cost">$ 13.05</p>
                <button class="btn btn-delete" aria-label="Delete item" type="button">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 140 139.9">
                    <title>close</title>
                    <path d="M3.4,136.6C-.4,132.8-1,129,1.6,125c.9-1.4,13.4-14.3,27.8-28.8L55.5,70,29.4,43.7C15,29.3,2.5,16.4,1.6,15-1,11-.4,7.2,3.4,3.4S11-1,15,1.6c1.4.9,14.3,13.4,28.7,27.8L70,55.5,96.2,29.4C110.7,15,123.6,2.5,125,1.6c4-2.6,7.8-2,11.6,1.8S141,11,138.4,15,21.2,133.6,16.6,137.1s-8.9,3.8-13.2-.5Zm120,.5c-4.6-3.4-34.4-33.4-36.8-37.1s-2-7.8,1.8-11.6S96,84,100,86.6s33.7,32.2,37.1,36.8,3.8,8.9-.5,13.2-7.9,4.4-13.2.5Z"/>
                  </svg>
                </button>
              </div>
            </div>
          </div>
          <div class="shop_card shoes container">
            <div class="image">
              <img src="~assets/images/skin1.png" alt="">
            </div>
            <div class="shop_card__inner container container--justify">
              <div class="shop_card__left container">
                <div class="description">
                  <h3>Nike Air | Jordans</h3>
                  <p>Size: <span>9,5</span></p>
                </div>
              </div>
              <div class="shop_card__right">
                <p class="cost">$ 13.05</p>
                <button class="btn btn-delete" aria-label="Delete item" type="button">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 140 139.9">
                    <title>close</title>
                    <path d="M3.4,136.6C-.4,132.8-1,129,1.6,125c.9-1.4,13.4-14.3,27.8-28.8L55.5,70,29.4,43.7C15,29.3,2.5,16.4,1.6,15-1,11-.4,7.2,3.4,3.4S11-1,15,1.6c1.4.9,14.3,13.4,28.7,27.8L70,55.5,96.2,29.4C110.7,15,123.6,2.5,125,1.6c4-2.6,7.8-2,11.6,1.8S141,11,138.4,15,21.2,133.6,16.6,137.1s-8.9,3.8-13.2-.5Zm120,.5c-4.6-3.4-34.4-33.4-36.8-37.1s-2-7.8,1.8-11.6S96,84,100,86.6s33.7,32.2,37.1,36.8,3.8,8.9-.5,13.2-7.9,4.4-13.2.5Z"/>
                  </svg>
                </button>
              </div>
            </div>
          </div>
          <div class="shop_card electronics container">
            <div class="image">
              <img src="~assets/images/skin1.png" alt="">
            </div>
            <div class="shop_card__inner container container--justify">
              <div class="shop_card__left container">
                <div class="description">
                  <h3>Gamepad</h3>
                  <p>XBOX One S</p>
                </div>
              </div>
              <div class="shop_card__right">
                <p class="cost">$ 13.05</p>
                <button class="btn btn-delete" aria-label="Delete item" type="button">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 140 139.9">
                    <title>close</title>
                    <path d="M3.4,136.6C-.4,132.8-1,129,1.6,125c.9-1.4,13.4-14.3,27.8-28.8L55.5,70,29.4,43.7C15,29.3,2.5,16.4,1.6,15-1,11-.4,7.2,3.4,3.4S11-1,15,1.6c1.4.9,14.3,13.4,28.7,27.8L70,55.5,96.2,29.4C110.7,15,123.6,2.5,125,1.6c4-2.6,7.8-2,11.6,1.8S141,11,138.4,15,21.2,133.6,16.6,137.1s-8.9,3.8-13.2-.5Zm120,.5c-4.6-3.4-34.4-33.4-36.8-37.1s-2-7.8,1.8-11.6S96,84,100,86.6s33.7,32.2,37.1,36.8,3.8,8.9-.5,13.2-7.9,4.4-13.2.5Z"/>
                  </svg>
                </button>
              </div>
            </div>
          </div>
          <div class="shop_card container">
            <div class="image">
              <img src="~assets/images/skin1.png" alt="">
            </div>
            <div class="shop_card__inner container container--justify">
              <div class="shop_card__left container">
                <div class="description">
                  <h3>WAX Key</h3>
                  <p>Wax items</p>
                </div>
                <div class="quantity">
                  <button class="btn btn-more" type="button" aria-label="Больше"
                          onclick="var i = this.parentNode.querySelector('.quantity_total').innerHTML;
                          i++; this.parentNode.querySelector('.quantity_total').innerHTML = i;">
                    <span></span></button>
                  <span class="quantity_total">1</span>
                  <button class="btn btn-less" type="button" aria-label="Меньше"
                          onclick="var i = this.parentNode.querySelector('.quantity_total').innerHTML;
                          if (i > 1) {i--; this.parentNode.querySelector('.quantity_total').innerHTML = i;}"><span></span></button>
                </div>
              </div>
              <div class="shop_card__right">
                <p class="cost">$ 13.05</p>
                <button class="btn btn-delete" aria-label="Delete item" type="button">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 140 139.9">
                    <title>close</title>
                    <path d="M3.4,136.6C-.4,132.8-1,129,1.6,125c.9-1.4,13.4-14.3,27.8-28.8L55.5,70,29.4,43.7C15,29.3,2.5,16.4,1.6,15-1,11-.4,7.2,3.4,3.4S11-1,15,1.6c1.4.9,14.3,13.4,28.7,27.8L70,55.5,96.2,29.4C110.7,15,123.6,2.5,125,1.6c4-2.6,7.8-2,11.6,1.8S141,11,138.4,15,21.2,133.6,16.6,137.1s-8.9,3.8-13.2-.5Zm120,.5c-4.6-3.4-34.4-33.4-36.8-37.1s-2-7.8,1.8-11.6S96,84,100,86.6s33.7,32.2,37.1,36.8,3.8,8.9-.5,13.2-7.9,4.4-13.2.5Z"/>
                  </svg>
                </button>
              </div>
            </div>
          </div>
        </div>
      </vue-scroll>
    </div>
    <div class="shop_footer container">
      <button class="btn btn-huge btn-buy" type="button">Купить</button>
    </div>
  </aside>
</template>

<script>
export default {
    components: {

    },
    name: '',
    data() {
        return {
            ops: {
                vuescroll: {
                    mode: 'native',
                    zooming: false
                },
                scrollPanel: {
                    scrollingX: false
                },
                rail: {
                    background: '#21222E',
                    opacity: 1,
                    border: 'none',
                    size: '5px',
                    keepShow: false
                },
                bar: {
                    background: 'linear-gradient(to bottom, #2af598, #08afe9)',
                    size: '5px',
                    keepShow: true
                }
            },
            products: [
                {
                    productTypeVGO: true,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: true,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: true,
                    productSaleSize: 3,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: true,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: true,
                    productSelected: false
                },
                {
                    productTypeVGO: true,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: true,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: true
                },
                {
                    productTypeVGO: false,
                    productTypeShoes: true,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: false,
                    productTypeShoes: true,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: false,
                    productTypeShoes: true,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: true,
                    productSelected: false
                },
                {
                    productTypeVGO: false,
                    productTypeShoes: true,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: false,
                    productTypeShoes: true,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: true
                },
                {
                    productTypeVGO: false,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: true,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: false,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: true,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: false,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: true,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: true,
                    productSelected: false
                },
                {
                    productTypeVGO: false,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: true,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: false,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: true,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: true
                },
                {
                    productTypeVGO: true,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: true,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: true,
                    productSaleSize: 3,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: true,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: true,
                    productSelected: false
                },
                {
                    productTypeVGO: true,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: false
                },
                {
                    productTypeVGO: true,
                    productTypeWears: false,
                    productTypeShoes: false,
                    productTypeElectronics: false,
                    productTypeStickers: false,
                    productSale: false,
                    productSaleSize: 0,
                    productHighPrice: false,
                    productSelected: true
                }
            ]
        }
    },
    methods: {}
}
</script>

<style lang="less">
  .p_shop-right {
    width: 30.8668%;
    padding: 0 0 134px;
    margin-left: 14px;
    position: relative;
    .shop_header {
      background: #272938;
      padding: 14px 29px;
      border-radius: 2px 2px 0 0;
      min-height: 64px;
      min-width: 500px;
      align-items: center;
      .shop_title {
        font-weight: 500;
        font-size: 17px;
        img {
          width: 17px;
          height: 16px;
          display: inline-block;
          margin-bottom: 0;
          margin-right: 4px;
        }
      }
      .shop_total {
        font-weight: 500;
        color: #777d97;
        span {
          display: inline-block;
          margin-left: 5px;
          color: #37d759;
          padding: 0 14px;
          white-space: nowrap;
          border-radius: 2px;
          background-color: rgb(22, 23, 31);
          line-height: 35px;
        }
      }
    }
    .shop_body {
      background: #16171f;
      padding: 29px 14px;
      flex-wrap: wrap;
      height: 100%;
      overflow-y: hidden;
      position: relative;
      .__vuescroll {
        width: calc(100% + 28px) !important;
        margin-right: -14px;
        margin-left: -14px;
          max-height: 500px;
        height: auto!important;
        .shop_container {
          flex-direction: column;
          padding: 15px 15px 29px;
        }
        .__rail-is-vertical {
          right: 0!important;
        }
        .__panel.__native {
          width: calc(100% + 17px);
          padding: 0 17px 0 0;
          .shop_container {
            padding: 0 14px;
          }
        }
      }
    }
    .shop_footer {
      margin-top: auto;
      background-color: rgb(39, 41, 56);
      border-radius: 0 0 2px 2px;
      padding: 29px;
      width: 100%;
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      .btn-buy {
        width: 100%;
        text-transform: uppercase;
        font-size: 25px;
        font-weight: 700;
        line-height: 1;
        padding: 14px;
        height: auto;
      }
    }
  }
  .shop_card {
    margin: 14px 14px 0;
    border-radius: 2px;
    background-color: rgb(39, 41, 56);
    min-height: 90px;
    .image {
      border-radius: 2px;
      background-color: rgb(29, 31, 42);
      width: 90px;
      padding: 14px;
      display: flex;
      justify-content: center;
      align-items: center;
      img {
        max-width: 100%;
        max-height: 100%;
        margin: auto;
      }
    }
    &__inner {
      width: calc(100% - 90px);
      padding: 14px 29px;
      align-items: center;
    }
    .description {
      font-weight: 500;
      margin-right: 14px;
      min-width: 100px;
      h3 {
        color: white;
        font-size: 20px;
      }
      p {
        color: #777d97;
        span {
          color: #5499e8;
        }
      }
    }
    .quantity {
      font-weight: 500;
      border: none;
      border-radius: 2px;
      background: rgb(22, 23, 31);
      line-height: 20px;
      padding: 4px 20px 6px 7px;
      text-align: center;
      display: inline-block;
      margin: 0 14px 0 0;
      color: #777d97;
      min-width: 54px;
      position: relative;
      .btn {
        padding: 3px;
        position: absolute;
        right: 7px;
        span {
          background: transparent;
          border: solid transparent;
          display: block;
          width: 8px;
          height: 5px;
        }
        &.btn-less {
          bottom: 50%;
          margin-bottom: -11px;
          span {
            border-width: 5px 4px 0 4px;
            border-top-color: #777d97;
          }
          &:hover, &:focus {
            span {
              border-top-color: white;
            }
          }
        }
        &.btn-more {
          top: 50%;
          margin-top: -11px;
          span {
            border-width: 0 4px 5px 4px;
            border-bottom-color: #777d97;
          }
          &:hover, &:focus {
            span {
              border-bottom-color: white;
            }
          }
        }
      }
    }
    &__left {
      align-items: center;
    }
    &__right {
      margin-left: auto;
      display: flex;
      align-items: center;
    }
    .cost {
      color: #37d759;
      font-size: 20px;
      font-weight: 700;
      white-space: nowrap;
    }
    .btn-delete {
      display: block;
      border-radius: 2px;
      background-color: rgb(231, 40, 40);
      width: 30px;
      height: 30px;
      margin-left: 14px;
      padding: 8px;
      svg {
        max-width: 100%;
        max-height: 100%;
        path {
          fill: white;
        }
      }
      &:hover, &:focus {
        background-color: rgb(22, 23, 31);
      }
    }
    &.electronics {
      .image {
        background-image: linear-gradient(to bottom left, #ff2825, #ffe23a);
      }
    }
  }
  @media screen and (max-width: 1640px) {
    .p_shop-right {
      width: 500px;
    }
  }
  @media screen and (max-width: 1200px) {
    .p_shop-right {
      .shop_header {
        padding-right: 14px;
        padding-left: 14px;
      }
    }
  }
  @media screen and (max-width: 1146px) {
    .p_shop-right {
      width: 100%;
      margin-left: 0;
      margin-top: 14px;
      .shop_body .__vuescroll .shop_container {
        flex-direction: row;
        flex-wrap: wrap;
      }
    }
    .shop_card {
        width: calc(50% - 28px);
        &__inner {
            padding: 14px;
        }
    }
  }
  @media screen and (max-width: 960px) {
    .p_shop-right {
      width: 100%;
      margin-left: 0;
      margin-top: 14px;
      .shop_body .__vuescroll .shop_container {
        flex-direction: row;
        flex-wrap: wrap;
      }
    }
    .shop_card {
      width: calc(100% - 28px);
        &__inner {
            padding: 14px 29px;
        }
    }
  }
  @media screen and (max-width: 680px) {
    .p_shop-right {
      .shop_header {
        flex-wrap: wrap;
        min-width: 0;
      }
    }
    .shop_card {
      margin-left: 0;
      margin-right: 0;
      width: 100%;
      &__inner {
        padding-left: 14px;
        padding-right: 14px;
        flex-direction: column;
      }
      &__left {
        width: 100%;
        flex-wrap: wrap;
      }
      .quantity {
        margin-left: auto;
        margin-bottom: 14px;
      }
      .description {
        margin-bottom: 14px;
      }
    }
  }
</style>

