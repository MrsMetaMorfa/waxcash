<template>
  <div class="block accumulation">
    <h2 class="accumulation_title">Накопительная система бонусов</h2>
    <p class="accumulation_text">Начни продавать скины и накапливать бонусы прямо сейчас!</p>
    <vue-scroll class="accumulation_progress" :ops="opsVertical">
      <div class="progress_wrapper">
        <ul class="container progress_badges">
          <li class="badge">
            <div class="badge_image">
              <img src="~assets/images/0.png" alt="Начинающий торгаш">
            </div>
            <p class="badge_description">Начинающий <br>торгаш</p>
          </li>
          <li class="badge">
            <div class="badge_image">
              <img src="~assets/images/1.png" alt="Юный трейдер">
            </div>
            <p class="badge_description">Юный <br>трейдер</p>
          </li>
          <li class="badge">
            <div class="badge_image">
              <img src="~assets/images/2.png" alt="Цифровой барыга">
            </div>
            <p class="badge_description">Цифровой <br>барыга</p>
          </li>
          <li class="badge">
            <div class="badge_image">
              <img src="~assets/images/3.png" alt="Прошареный парень">
            </div>
            <div class="badge_description">Прошареный <br>парень</div>
          </li>
          <li class="badge">
            <div class="badge_image">
              <img src="~assets/images/4.png" alt="Ликвидатор скинов">
            </div>
            <p class="badge_description">Ликвидатор <br>скинов</p>
          </li>
          <li class="badge close">
            <div class="badge_image">
              <img src="~assets/images/5.png" alt="Скин-дилер">
            </div>
            <div class="badge_description">Скин <br>дилер</div>
          </li>
          <li class="badge close">
            <div class="badge_image">
              <img src="~assets/images/6.png" alt="Гроза рулеток">
            </div>
            <p class="badge_description">Гроза <br>рулеток</p>
          </li>
          <li class="badge close">
            <div class="badge_image">
              <img src="~assets/images/7.png" alt="Ценитель флоата">
            </div>
            <p class="badge_description">Ценитель <br>флоата</p>
          </li>
          <li class="badge close">
            <div class="badge_image">
              <img src="~assets/images/8.png" alt="Большой босс">
            </div>
            <p class="badge_description">Большой <br>босс</p>
          </li>
          <li class="badge close">
            <div class="badge_image">
              <img src="~assets/images/9.png" alt="Всемирная элита">
            </div>
            <p class="badge_description">Всемирная <br>элита</p>
          </li>
          <li class="badge close">
            <div class="badge_image">
              <img src="~assets/images/10.png" alt="WAX Лорд">
            </div>
            <p class="badge_description">WAX <br>Лорд</p>
          </li>
        </ul>
        <div class="container progress_bar">
          <div class="bar">
            <div style="width: calc(42% + 30px)"></div>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1276 30">
              <title>bar</title>
              <path d="M0,0V30H1276V0ZM1275.3,20.6a2.9,2.9,0,0,1-1.5,2.5l-9.3,5.4a3,3,0,0,1-2.9,0l-10.9-6.2V22H1150.3v.3l-10.8,6.2a3,3,0,0,1-2.9,0l-10.9-6.2V22H1025.3v.3l-10.8,6.2a3,3,0,0,1-2.9,0l-10.9-6.2V22H900.3v.3l-10.8,6.2a3,3,0,0,1-2.9,0l-10.9-6.2V22H775.3v.3l-10.8,6.2a3,3,0,0,1-2.9,0l-10.9-6.2V22H650.3v.3l-10.8,6.2a3,3,0,0,1-2.9,0l-10.9-6.2V22H525.3v.3l-10.8,6.2a3,3,0,0,1-2.9,0l-10.9-6.2V22H400.3v.3l-10.8,6.2a3,3,0,0,1-2.9,0l-10.9-6.2V22H275.3v.3l-10.8,6.2a3,3,0,0,1-2.9,0l-10.9-6.2V22H150.3v.3l-10.8,6.2a3,3,0,0,1-2.9,0l-10.9-6.2V22H25.3v.3L14.5,28.5a3,3,0,0,1-2.9,0L2.2,23.1A2.9,2.9,0,0,1,.7,20.6V9.8A3.1,3.1,0,0,1,2.2,7.2l9.4-5.4a3,3,0,0,1,2.9,0l10,5.8a2.3,2.3,0,0,0,1.4.4h99.2a2.8,2.8,0,0,0,1.5-.4l10-5.8a3,3,0,0,1,2.9,0l10,5.8a2.3,2.3,0,0,0,1.4.4h99.2a2.8,2.8,0,0,0,1.5-.4l10-5.8a3,3,0,0,1,2.9,0l10,5.8a2.3,2.3,0,0,0,1.4.4h99.2a2.8,2.8,0,0,0,1.5-.4l10-5.8a3,3,0,0,1,2.9,0l10,5.8a2.3,2.3,0,0,0,1.4.4h99.2a2.8,2.8,0,0,0,1.5-.4l10-5.8a3,3,0,0,1,2.9,0l10,5.8a2.3,2.3,0,0,0,1.4.4h99.2a2.8,2.8,0,0,0,1.5-.4l10-5.8a3,3,0,0,1,2.9,0l10,5.8a2.3,2.3,0,0,0,1.4.4h99.2a2.8,2.8,0,0,0,1.5-.4l10-5.8a3,3,0,0,1,2.9,0l10,5.8a2.3,2.3,0,0,0,1.4.4h99.2a2.8,2.8,0,0,0,1.5-.4l10-5.8a3,3,0,0,1,2.9,0l10,5.8a2.3,2.3,0,0,0,1.4.4h99.2a2.8,2.8,0,0,0,1.5-.4l10-5.8a3,3,0,0,1,2.9,0l10,5.8a2.3,2.3,0,0,0,1.4.4h99.2a2.8,2.8,0,0,0,1.5-.4l10-5.8a3,3,0,0,1,2.9,0l10,5.8a2.3,2.3,0,0,0,1.4.4h99.2a2.8,2.8,0,0,0,1.5-.4l10-5.8a3,3,0,0,1,2.9,0l9.3,5.4a3.1,3.1,0,0,1,1.5,2.6Z"/>
            </svg>
          </div>
        </div>
        <ul class="container progress_sums">
          <li>1Р</li>
          <li>1000Р</li>
          <li>2000Р</li>
          <li>3000Р</li>
          <li>4000Р</li>
          <li class="close">5000Р</li>
          <li class="close">6000Р</li>
          <li class="close">7000Р</li>
          <li class="close">8000Р</li>
          <li class="close">9000Р</li>
          <li class="close">10000Р</li>
        </ul>
      </div>
    </vue-scroll>
    <ul class="container accumulation_badges">
      <li class="container block_light active">
        <div class="badge_image">
          <img src="~assets/images/0.png" alt="Начинающий торгаш">
        </div>
        <div class="badge_description">
          <h3>Начинающий торгаш</h3>
          <p>Необходимо совершить сделок на 1 рубль.
            Размер скидки - <span>0%</span></p>
        </div>
        <div class="mark">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 13.4 10.9">
            <title>check-mark-01</title>
            <path d="M13.4,1.5,5.7,10.9,0,4.9,1.6,3.3,5.5,7.5,11.8,0Z"/>
          </svg>
        </div>
      </li>
      <li class="container block_light active">
        <div class="badge_image">
          <img src="~assets/images/1.png" alt="Юный трейдер">
        </div>
        <div class="badge_description">
          <h3>Юный трейдер</h3>
          <p>Необходимо совершить сделок на 1000 рубль.
            Размер скидки - <span>0.5%</span></p>
        </div>
        <div class="mark">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 13.4 10.9">
            <title>check-mark-01</title>
            <path d="M13.4,1.5,5.7,10.9,0,4.9,1.6,3.3,5.5,7.5,11.8,0Z"/>
          </svg>
        </div>
      </li>
      <li class="container block_light active">
        <div class="badge_image">
          <img src="~assets/images/2.png" alt="Цифровой барыга">
        </div>
        <div class="badge_description">
          <h3>Цифровой барыга</h3>
          <p>Необходимо совершить сделок на 2000 рубль.
            Размер скидки - <span>1%</span></p>
        </div>
        <div class="mark">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 13.4 10.9">
            <title>check-mark-01</title>
            <path d="M13.4,1.5,5.7,10.9,0,4.9,1.6,3.3,5.5,7.5,11.8,0Z"/>
          </svg>
        </div>
      </li>
      <li class="container block_light active">
        <div class="badge_image">
          <img src="~assets/images/3.png" alt="Прошареный парень">
        </div>
        <div class="badge_description">
          <h3>Прошареный парень</h3>
          <p>Необходимо совершить сделок на 3000 рубль.
            Размер скидки - <span>1.5%</span></p>
        </div>
        <div class="mark">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 13.4 10.9">
            <title>check-mark-01</title>
            <path d="M13.4,1.5,5.7,10.9,0,4.9,1.6,3.3,5.5,7.5,11.8,0Z"/>
          </svg>
        </div>
      </li>
      <li class="container block_light active">
        <div class="badge_image">
          <img src="~assets/images/4.png" alt="Ликвидатор скинов">
        </div>
        <div class="badge_description">
          <h3>Ликвидатор скинов</h3>
          <p>Необходимо совершить сделок на 4000 рубль.
            Размер скидки - <span>2%</span></p>
        </div>
        <div class="mark">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 13.4 10.9">
            <title>check-mark-01</title>
            <path d="M13.4,1.5,5.7,10.9,0,4.9,1.6,3.3,5.5,7.5,11.8,0Z"/>
          </svg>
        </div>
      </li>
      <li class="container block_light">
        <div class="badge_image">
          <img src="~assets/images/5.png" alt="Скин-дилер">
        </div>
        <div class="badge_description">
          <h3>Скин-дилер</h3>
          <p>Необходимо совершить сделок на 5000 рубль.
            Размер скидки - <span>2.5%</span></p>
        </div>
      </li>
      <li class="container block_light">
        <div class="badge_image">
          <img src="~assets/images/6.png" alt="Гроза рулеток">
        </div>
        <div class="badge_description">
          <h3>Гроза рулеток</h3>
          <p>Необходимо совершить сделок на 6000 рубль.
            Размер скидки - <span>3%</span></p>
        </div>
      </li>
      <li class="container block_light">
        <div class="badge_image">
          <img src="~assets/images/7.png" alt="Ценитель флоата">
        </div>
        <div class="badge_description">
          <h3>Ценитель флоата</h3>
          <p>Необходимо совершить сделок на 7000 рубль.
            Размер скидки - <span>3.5%</span></p>
        </div>
      </li>
      <li class="container block_light">
        <div class="badge_image">
          <img src="~assets/images/8.png" alt="Большой босс">
        </div>
        <div class="badge_description">
          <h3>Большой босс</h3>
          <p>Необходимо совершить сделок на 8000 рубль.
            Размер скидки - <span>4%</span></p>
        </div>
      </li>
      <li class="container block_light">
        <div class="badge_image">
          <img src="~assets/images/9.png" alt="Всемирная элита">
        </div>
        <div class="badge_description">
          <h3>Всемирная элита</h3>
          <p>Необходимо совершить сделок на 9000 рубль.
            Размер скидки - <span>4.5%</span></p>
        </div>
      </li>
      <li class="container block_light">
        <div class="badge_image">
          <img src="~assets/images/10.png" alt="WAX Лорд">
        </div>
        <div class="badge_description">
          <h3>WAX Лорд</h3>
          <p>Необходимо совершить сделок на 10000 рубль.
            Размер скидки - <span>5%</span></p>
        </div>
      </li>
    </ul>
  </div>
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
  .accumulation {
    width: 100%;
    padding: 29px;
    &_title {
      font-size: 33px;
      margin-bottom: 14px;
      padding-top: 29px;
      text-align: center;
    }
    &_text {
      font-size: 25px;
      color: #777d97;
      text-align: center;
    }
    &_progress {
      height: auto!important;
      margin: 29px auto;
      max-width: 1375px;
      .progress_wrapper {
        min-width: 1375px;
        padding-bottom: 29px;
      }
      .progress_badges {
        padding: 0;
        list-style-type: none;
        margin-bottom: 29px;
        .badge {
          width: 125px;
          &_image {
            width: 56px;
            margin: 0 auto 14px;
          }
          &_description {
            text-align: center;
          }
          &.close {
            .badge_image {
              img {
                filter: grayscale(100%);
              }
            }
            .badge_description {
              color: #777d97;
            }
          }
        }
      }
      .progress_sums {
        padding: 0;
        list-style-type: none;
        margin-top: 29px;
        li {
          width: 125px;
          text-align: center;
          color: #38d75a;
          &.close {
            color: #777d97;
          }
        }
      }
      .progress_bar {
        background-color: #272938;
        height: 70px;
        border-radius: 45px;
        padding: 20px 50px;
        .bar {
          height: 30px;
          width: 100%;
          background: #20212D;
          overflow: hidden;
          position: relative;
          div {
            background: #57CA85 linear-gradient(to right, #184e68, #57CA85);
            background-size: 100% 100%;
            height: calc(100% - 2px);
            border-radius: 15px;
            margin: 1px auto 1px -15px;
          }
          svg {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            path {
              fill: #272938;
            }
          }
        }
      }
      .__panel.__native {
        margin-bottom: -21px;
        padding-bottom: 21px;
      }
    }
    &_badges {
      flex-wrap: wrap;
      justify-content: center;
      padding: 0;
      max-width: 1375px;
      margin: 0 auto;
      li {
        width: calc(50% - 28px);
        max-width: 660px;
        margin: 0 14px 14px;
        align-items: center;
        position: relative;
        .badge_image {
          border-radius: 2px;
          background-color: rgb(32, 33, 45);
          height: 100%;
          display: flex;
          justify-content: center;
          align-items: center;
          padding: 14px 20px;
          img {
            width: 70px;
            min-width: 70px;
          }
        }
        .badge_description {
          padding: 14px 108px 14px 29px;
          h3 {
            font-size: 24px;
            margin-bottom: 7px;
            font-weight: 600;
          }
          p {
            color: #777d97;
            span {
              color: #5499e8;
            }
          }
        }
        &.active .mark {
          display: flex;
          justify-content: center;
          align-items: center;
          position: absolute;
          right: 29px;
          top: 50%;
          background: rgba(56,223,90,.15);
          border-radius: 50%;
          width: 50px;
          height: 50px;
          margin-top: -25px;
          padding: 11px 10px;
          svg {
            width: 100%;
            path {
              fill: #38DF5A;
            }
          }
        }
      }
    }
  }
  @media screen and (max-width: 1020px) {
    .accumulation {
      &_badges {
        li {
          width: 100%;
          margin-left: 0;
          margin-right: 0;
        }
      }
    }
  }
  @media screen and (max-width: 540px) {
    .accumulation {
      padding: 29px 14px;
      &_badges {
        li {
          .badge_image {
            padding-left: 10px;
            padding-right: 10px;
            img {
              min-width: 40px;
            }
          }
          .badge_description {
            padding-left: 14px;
            padding-right: 68px;
            h3 {
              font-size: 20px;
            }
          }
          &.active .mark {
            width: 30px;
            height: 30px;
            margin-top: -15px;
            right: 14px;
          }
        }
      }
    }
  }
  @media screen and (max-width: 375px) {
    .accumulation {
      &_badges {
        li {
          .badge_image {
            padding-left: 10px;
            padding-right: 10px;
            align-items: flex-start;
            img {
              min-width: 40px;
            }
          }
          .badge_description {
            padding-left: 14px;
            padding-right: 14px;
            h3 {
              font-size: 20px;
            }
          }
          &.active .mark {
            right: auto;
            left: 15px;
            top: auto;
            bottom: 14px;
            width: 30px;
            height: 30px;
            margin-top: 0;
          }
        }
      }
    }
  }
</style>

