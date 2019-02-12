<template>
  <div class="order" id="modalOrder">
    <div class="block">
      <div class="order_total container">
        <div class="image_wrapper">
          <img src="~assets/icons/wallet-gradient.svg" alt="">
        </div>
        <div class="order_description">
          <h2><span class="total">12 350.08</span> Рублей</h2>
          <p>Вы получите на свой кошелек</p>
        </div>
      </div>
      <div class="order_details">
        <h2>Детали заказа</h2>
        <p class="line container container--justify">
          <span class="label">Номер заказа:</span>
          <span class="value">1454574-51UZ-K1BS-WTOS</span>
        </p>
        <p class="line container container--justify">
          <span class="label">Email:</span>
          <span class="value">admin@waxcash.net</span>
        </p>
        <p class="line container container--justify">
          <span class="label">Кошелек:</span>
          <span class="value">XXXX XXXX XXXX 6589</span>
        </p>
      </div>
    </div>
    <div class="divider"></div>
    <div class="block order_status">
        <p class="line container container--justify">
          <span class="label">Статус платежа:</span>
          <span class="value success">Отправлено</span>
        </p>
        <p class="line container container--justify">
          <span class="label">Статус трейда:</span>
          <span class="value waiting">Ожидает подтверждения...</span>
        </p>
        <button class="btn btn-huge" type="button"
                onclick="document.querySelector('#modalOrder').classList.remove('active');
                          document.querySelector('#modalNotification').classList.add('active');"
                :getStartTimer="getStartTimer"
        >ПРИНЯТЬ ТРЕЙД</button>
      </div>
    <div class="divider notch"></div>
    <div class="block order_extra">
      <button class="btn btn-opacity container" type="button">
        Оставьте отзыв на
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1132.8 278.2">
          <title>Trustpilot</title>
          <path class="logo" d="M297.7,98.6H412.5V120H367.4V240.3H342.6V120H297.7Zm109.8,39.1h21.2v19.8h.4a24.1,24.1,0,0,1,3.9-8.1,38.4,38.4,0,0,1,16-12.5,27.5,27.5,0,0,1,10.1-2l5.5.2,3.1.4v21.8l-4.9-.7-4.9-.3a26.5,26.5,0,0,0-10.8,2.3,24.1,24.1,0,0,0-8.8,6.8,34,34,0,0,0-6,11,49.5,49.5,0,0,0-2.2,15.1v48.8H407.5Zm164,102.6H549.3V226h-.4a30.8,30.8,0,0,1-12.4,12.4,33.9,33.9,0,0,1-16.8,4.7c-13.5,0-23.3-3.4-29.3-10s-9-16.8-9-30.3V137.7H504v62.9c0,9,1.7,15.4,5.2,19.1s8.2,5.5,14.5,5.5a28.1,28.1,0,0,0,11.9-2.2,21.5,21.5,0,0,0,7.7-5.8,23.4,23.4,0,0,0,4.3-8.8,49.8,49.8,0,0,0,1.3-11.2V137.7h22.6ZM610,207.4c.7,6.6,3.2,11.2,7.5,13.9a30.2,30.2,0,0,0,15.7,3.9,49.7,49.7,0,0,0,7.3-.5,27.3,27.3,0,0,0,7.6-1.9,13.8,13.8,0,0,0,5.9-4,10.2,10.2,0,0,0,2.1-7.1,10,10,0,0,0-3.2-7.1,21.5,21.5,0,0,0-7.7-4.5,76.3,76.3,0,0,0-10.6-2.9l-12.1-2.5c-4.2-1-8.3-2.1-12.2-3.4a37.2,37.2,0,0,1-10.5-5.4,25,25,0,0,1-7.5-8.6,28.4,28.4,0,0,1-2.7-13c0-5.6,1.3-10.2,4-14a30.5,30.5,0,0,1,10.4-9.1,42,42,0,0,1,13.8-4.9,84.6,84.6,0,0,1,14.6-1.4,68.1,68.1,0,0,1,15.2,1.7,38.3,38.3,0,0,1,13.1,5.5,30.3,30.3,0,0,1,9.7,9.8,34.1,34.1,0,0,1,4.9,14.6H651.7c-1.1-5.5-3.6-9.1-7.5-11a31.4,31.4,0,0,0-13.4-2.7,41.8,41.8,0,0,0-5.6.4,21.6,21.6,0,0,0-6.2,1.5,12.1,12.1,0,0,0-4.8,3.1,7.7,7.7,0,0,0-2,5.5,8.2,8.2,0,0,0,2.9,6.7,20.8,20.8,0,0,0,7.5,4.3,80.4,80.4,0,0,0,10.6,2.9c4,.8,8.1,1.6,12.3,2.6a119.6,119.6,0,0,1,12.1,3.3,42.9,42.9,0,0,1,10.7,5.4,26.6,26.6,0,0,1,7.5,8.5,26.2,26.2,0,0,1,2.9,12.7c0,6.1-1.4,11.3-4.2,15.5a32.2,32.2,0,0,1-10.8,10.3,48.1,48.1,0,0,1-14.8,5.8,74.3,74.3,0,0,1-16.1,1.8,67.5,67.5,0,0,1-17.9-2.2,43.8,43.8,0,0,1-14.3-6.6,32.4,32.4,0,0,1-9.6-11.2,35,35,0,0,1-3.6-15.7Zm74.6-69.7h17.1V106.9h22.6v30.8h20.5v16.9H724.3v54.7a54.6,54.6,0,0,0,.3,6.2,11.4,11.4,0,0,0,1.4,4.4,6.7,6.7,0,0,0,3.3,2.6,16.1,16.1,0,0,0,6,.9H740a19.9,19.9,0,0,0,4.8-.7v17.5l-7.4.8a57.4,57.4,0,0,1-7.3.4,50.6,50.6,0,0,1-14.4-1.7,19.5,19.5,0,0,1-8.5-4.9,16.8,16.8,0,0,1-4.2-8.3,61.7,61.7,0,0,1-1.3-11.3V154.6H684.6Zm76.1,0h21.4v13.9h.4a27.9,27.9,0,0,1,13.3-12.8,43.8,43.8,0,0,1,18.5-3.9c8,0,15.1,1.4,21.1,4.3a41.2,41.2,0,0,1,15,11.7,49.4,49.4,0,0,1,8.9,17.4,72.4,72.4,0,0,1,3,21.2,73.7,73.7,0,0,1-2.7,20,53.5,53.5,0,0,1-8.1,17.2,41.6,41.6,0,0,1-13.8,11.9,40.9,40.9,0,0,1-19.7,4.5,55.2,55.2,0,0,1-9.9-.9,43.6,43.6,0,0,1-9.5-2.9,38,38,0,0,1-8.5-5,29.8,29.8,0,0,1-6.4-7.3h-.4v51.2H760.7Zm79,51.4a51.1,51.1,0,0,0-1.8-13.5,36.4,36.4,0,0,0-5.4-11.6,27.9,27.9,0,0,0-8.9-8.2,24.9,24.9,0,0,0-12.3-3q-14.2,0-21.6,9.9t-7.2,26.4a50.7,50.7,0,0,0,1.9,14.4,32,32,0,0,0,5.6,11.4,28.4,28.4,0,0,0,9.1,7.5,25,25,0,0,0,12.2,2.8c5.1,0,9.5-1,13.1-3.2a26.6,26.6,0,0,0,8.8-8.2,34.1,34.1,0,0,0,5-11.5A58.1,58.1,0,0,0,839.7,189.1Zm39.9-90.5h22.6V120H879.6Zm0,39.1h22.6V240.3H879.6Zm42.8-39.1H945V240.3H922.4Zm91.9,144.5a55.9,55.9,0,0,1-21.9-4.1,46.1,46.1,0,0,1-16.3-11.2A47.9,47.9,0,0,1,966,210.7a66,66,0,0,1-3.5-21.8,65.2,65.2,0,0,1,3.5-21.6,47.9,47.9,0,0,1,10.1-17.1A46.1,46.1,0,0,1,992.4,139a55.9,55.9,0,0,1,21.9-4.1,56.8,56.8,0,0,1,22,4.1,45.7,45.7,0,0,1,16.2,11.2,48.1,48.1,0,0,1,10.2,17.1,65.2,65.2,0,0,1,3.4,21.6,66,66,0,0,1-3.4,21.8,48.1,48.1,0,0,1-10.2,17.1,45.7,45.7,0,0,1-16.2,11.2A56.8,56.8,0,0,1,1014.3,243.1Zm0-17.9a25,25,0,0,0,13.1-3.2,27.1,27.1,0,0,0,9.2-8.3,37.1,37.1,0,0,0,5.2-11.6,51.7,51.7,0,0,0,0-26.3,36.1,36.1,0,0,0-5.2-11.6,29.4,29.4,0,0,0-9.2-8.3,29.2,29.2,0,0,0-26.2,0,29,29,0,0,0-9.1,8.3,36.2,36.2,0,0,0-5.3,11.6,51.7,51.7,0,0,0,0,26.3,37.3,37.3,0,0,0,5.3,11.6,26.8,26.8,0,0,0,9.1,8.3A25.2,25.2,0,0,0,1014.3,225.2Zm58.4-87.5h17.1V106.9h22.6v30.8h20.4v16.9h-20.4v54.7a54.6,54.6,0,0,0,.3,6.2,9.9,9.9,0,0,0,1.4,4.4,6.4,6.4,0,0,0,3.2,2.6,16.5,16.5,0,0,0,6,.9h4.8a19.8,19.8,0,0,0,4.7-.7v17.5l-7.3.8a60.1,60.1,0,0,1-7.4.4,51.6,51.6,0,0,1-14.4-1.7,20.1,20.1,0,0,1-8.5-4.9,18.7,18.7,0,0,1-4.2-8.3,62.2,62.2,0,0,1-1.2-11.3V154.6h-17.1Z"/>
          <path class="star" d="M135.7,197.1l59-15.3L219.5,258ZM271.3,98.6H167.7L135.7,0,103.6,98.6H0l83.9,61L51.8,258l83.9-60.9,51.8-37.6,83.8-60.9Z"/>
        </svg>
      </button>
      <p class="hint">
        <span class="icon"></span>
        Возникли проблемы с заказом? Наши агенты
        поддержки помогут вам решить любой вопрос!
      </p>
      <button class="btn btn-bright" type="button">НАПИСАТЬ В ПОДДЕРЖКУ</button>
      <p class="site"><a href="//waxcash.net">www.waxcash.net</a></p>
    </div>
  </div>
</template>

<script>
    export default {
        data() {
            return {
                getStartTimer: true
            }
        }
    }
</script>

<style lang="less">
  .order {
    border-radius: 2px;
    padding: 29px 0;
    position: relative;
    overflow: hidden;
    width: 100%;
    max-width: 618px;
    margin: auto!important;
    max-height: 962px;
    display: none;
    .block {
      border-radius: 0;
      margin-bottom: 0!important;
      &:first-of-type {
        padding-top: 29px;
      }
    }
    &_total {
      margin: 0 0 29px;
      background: #57b18e url("~assets/images/order-total-bg.jpg") no-repeat center;
      background-size: cover;
      padding: 14px 60px;
      align-items: center;
      .image_wrapper {
        width: 100px;
        height: 100px;
        margin-right: 42px;
        img {
          max-width: 100%;
        }
      }
      .order_description {
        width: calc(100% - 142px);
        h2 {
          text-shadow: 0 6px 7px rgba(0, 0, 0, 0.25);
          font-size: 35px;
          margin-bottom: 14px;
          .total {
            color: #38D75A;
          }
        }
        p {
          font-size: 21px;
          text-shadow: 0 6px 7px rgba(0, 0, 0, 0.25);
        }
      }
    }
    &_details {
      padding: 0 60px 0;
      h2 {
        font-size: 33px;
        margin-bottom: 14px;
      }
    }
    &_status {
      padding: 0 60px 0;
      .btn-huge {
        width: 100%;
        margin-top: 14px;
        height: auto;
        font-size: 25px;
        font-weight: 700;
        text-transform: uppercase;
        padding: 16px 14px 12px;
        border: 1px solid #38d75a;
        &:hover, &:focus {
          background: transparent;
        }
      }
    }
    &_extra {
      padding: 0 60px 29px;
      background-image: linear-gradient( to right, rgb(24,78,104) 0%, rgb(87,202,133) 100%);
      background-position: left bottom;
      background-size: 100% 5px;
      background-repeat: no-repeat;
      .btn-opacity {
        border: 1px solid #00B67A;
        border-radius: 2px;
        padding: 8px 29px 14px;
        font-size: 22px;
        font-weight: 600;
        width: 100%;
        justify-content: center;
        align-items: flex-end;
        margin-bottom: 29px;
        svg {
          height: 36px;
          margin-left: 5px;
          .star {
            fill: #00b67a;
          }
          .logo {
            fill: white;
          }
        }
        &:hover, &:focus {
          background: #00B67A;
          svg {
            .star {
              fill: white;
            }
          }
        }
      }
      .hint {
        margin-bottom: 14px;
        color: #777d97;
        font-size: 18px;
        line-height: 1.44444;
        padding-left: 64px;
        position: relative;
        .icon {
          display: flex;
          flex-direction: column;
          align-items: center;
          justify-content: center;
          position: absolute;
          top: 50%;
          left: 0;
          margin-top: -23px;
          width: 46px;
          height: 46px;
          border-radius: 50%;
          background: #777d97;
          &:before, &:after {
            content: '';
            display: block;
            width: 6px;
            background: #16171f;
            border-radius: 3px;
          }
          &:before {
            height: 6px;
          }
          &:after {
            height: 19px;
            margin-top: 1px;
          }
        }
      }
      .btn-bright {
        width: 100%;
        font-size: 25px;
        font-weight: 700;
        text-transform: uppercase;
        padding: 16px 14px 12px;
        margin-bottom: 14px;
        border: 1px solid #5499E8;
      }
      .site {
        text-align: center;
        a {
          text-decoration: none;
          opacity: 0.1;
          color: white;
          font-size: 20px;
          border-bottom: 1px solid transparent;
          display: inline-block;
          &:hover, &:after {
            opacity: 0.2;
            border-bottom-color: white;
          }
        }
      }
    }
    .line {
      color: #777d97;
      font-size: 20px;
      &:not(:last-of-type) {
        margin-bottom: 14px;
      }
      .value {
        color: #5499e8;
        &.success {
          color: #38d75a;
        }
        &.error {
          color: #e62927;
        }
        &.waiting {
          color: #5499e8;
        }
      }
    }
    &.active {
      display: block;
    }
  }
  .divider {
    padding: 25px 10px;
    background: #16171f;
    &:before {
      content: '';
      display: block;
      width: 100%;
      height: 2px;
      background: linear-gradient(to left, #272938 25%, transparent 25%, transparent 75%, #272938 75%) repeat-x center;
      background-size: 20px 100%;
    }
    &.notch {
      background: #16171f ;
      background: radial-gradient(ellipse at 0 50%, transparent 20px, #16171f 0),
                  radial-gradient(ellipse at 100% 50%, transparent 20px, #16171f 0);
      background-position: center left, center right;
      background-size: 60% 1400%;
      background-repeat: no-repeat;
      padding: 25px 30px;
    }
  }
  @media screen and (max-width: 590px) {
    .order_total, .order_status, .order_details, .order_extra {
      padding-left: 29px;
      padding-right: 29px;
    }
    .order_total {
      .image_wrapper {
        margin-right: 14px;
      }
      .order_description {
        width: calc(100% - 114px);
      }
    }
  }
  @media screen and (max-width: 504px) {
    .order {
      max-height: 100%;
    }
    .order_total {
      flex-direction: column;
      align-items: center;
      .order_description {
        width: 100%;
        margin-top: 14px;
        text-align: center;
        h3 {
          font-size: 80%;
        }
      }
    }
    .order_details {
      h2 {
        font-size: 30px;
      }
    }
    .order_extra {
      .btn-opacity {
        flex-direction: column;
        align-items: center;
      }
    }
    .line {
      flex-direction: column;
      .value {
        margin-left: auto;
        text-align: right;
      }
    }
  }
</style>

