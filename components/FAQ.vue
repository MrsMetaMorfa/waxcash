<template>
  <div class="block container faq_wrapper">
    <h2>FAQ</h2>
    <main class="faq_main">
      <ul class="faq_main__list">
        <li class="faq_main__list-item block_light">
          <h3 onclick="this.parentNode.classList.toggle('open')">Как пользоваться нашим сервисом? <span class="icon"></span></h3>
          <div class="inner">
            <p>Деньги зачисляются на счет в течении 20 минут. Наш сервис работает круглосуточно и в полуавтоматическом режиме.</p>
          </div>
        </li>
        <li class="faq_main__list-item block_light">
          <h3 onclick="this.parentNode.classList.toggle('open')">Как быстро я получу свои средства? <span class="icon"></span></h3>
          <div class="inner">
            <p>Деньги зачисляются на счет в течении 20 минут. Наш сервис работает круглосуточно и в полуавтоматическом режиме.</p>
          </div>
        </li>
        <li class="faq_main__list-item block_light">
          <h3 onclick="this.parentNode.classList.toggle('open')">Какая коммисия? <span class="icon"></span></h3>
          <div class="inner">
            <p>Деньги зачисляются на счет в течении 20 минут. Наш сервис работает круглосуточно и в полуавтоматическом режиме.</p>
          </div>
        </li>
        <li class="faq_main__list-item block_light">
          <h3 onclick="this.parentNode.classList.toggle('open')">Как считается реферальный уровень? <span class="icon"></span></h3>
          <div class="inner">
            <p>Вы должны пригласить определенное количество людей для повышения уровня. Ниже представлена таблица уровней.</p>
            <ul>
              <li>1 уровень - 1% от суммы сделки (от 0 до 200 рефералов)</li>
              <li>2 уровень - 2% от суммы сделки (от 200 до 500 рефералов)</li>
              <li>3 уровень - 3% от суммы сделки (от 500 до 1000 рефералов)</li>
              <li>4 уровень - 4% от суммы сделки (от 1000до 5000 рефералов)</li>
              <li>5 уровень - 5% от суммы сделки (от 5000 рефералов)</li>
            </ul>
          </div>
        </li>
        <li class="faq_main__list-item block_light">
          <h3 onclick="this.parentNode.classList.toggle('open')">Где я могу получить ответы на свои вопросы? <span class="icon"></span></h3>
          <div class="inner">
            <p>Деньги зачисляются на счет в течении 20 минут. Наш сервис работает круглосуточно и в полуавтоматическом режиме.</p>
          </div>
        </li>
      </ul>
    </main>
    <aside class="faq_aside">
      <div class="container block_light">
        <div class="image_wrapper">
          <img src="~assets/icons/goal.svg" alt="Support agents">
        </div>
        <div class="description_wrapper">
          <h3>Остались вопросы?</h3>
          <p>Не нашли ответа на свой вопрос на этой странице? Агенты поддержки помогут вам :)</p>
          <button class="btn btn-bright" type="button">ЗАДАТЬ ВОПРОС</button>
        </div>
      </div>
      <div class="container block_light">
        <div class="image_wrapper">
          <img src="~assets/icons/youtube.svg" alt="YouTube">
        </div>
        <div class="description_wrapper">
          <h3>Гайд по работе с сайтом</h3>
          <p>Если у вас возникли вопросы касательно
            процедуры покупки или продажи предметов
            на нашем сайте - посмотрите это видео. В нем
            мы постарались максимально подробно
            показать весь процесс от начала до конца.</p>
          <button class="btn btn-bright" type="button">СМОТРЕТЬ</button>
        </div>
      </div>
    </aside>
  </div>
</template>

<script>
    export default {
        data() {
            return {
            }
        }
    }
</script>

<style lang="less">
  .faq_wrapper {
    width: 100%;
    padding: 29px;
    flex-wrap: wrap;
    align-content: flex-start;
    h2 {
      width: 100%;
      margin-bottom: 14px;
      padding: 0 29px;
    }
    .block_light {
      padding: 14px 29px;
      margin-bottom: 14px;
    }
  }
  .faq_main {
    width: 67%;
    &__list {
      list-style-type: none;
      padding-left: 0;
      &-item {
        padding: 0!important;
        h3 {
          position: relative;
          font-weight: 400;
          padding: 14px 68px 14px 29px;
          cursor: pointer;
          line-height: 25px;
          .icon {
            position: absolute;
            width: 25px;
            height: 25px;
            display: block;
            top: 14px;
            right: 29px;
            background: url("~assets/icons/arrow.svg") no-repeat center;
            background-size: 100% 100%;
          }
        }
        .inner {
          //height: 0;
          max-height: 0;
          overflow: hidden;
          color: #777d97;
          padding: 0 50px;
          //transform-origin: center top;
          //transform: scaleY(0);
          transition: max-height 0.5s ease-out, padding-bottom 0.3s ease-in;
          ul {
            list-style: none;
            padding: 0;
            margin-top: 14px;
            li {
              color: #777d97;
              padding-left: 29px;
              padding-bottom: 7px;
              position: relative;
              &:after {
                content: '';
                display: block;
                background: #5499e8;
                width: 6px;
                height: 6px;
                border-radius: 50%;
                top: 50%;
                left: 0;
                margin-top: -3px;
                position: absolute;
              }
            }
          }
        }
        &.open {
          h3 {
            color: #5499e8;
            .icon {
              background: url("~assets/icons/close.svg") no-repeat center;
              background-size: 100% 100%;
            }
          }
          .inner {
            //height: auto;
            max-height: 300px;
            padding-bottom: 14px;
            //transform: scaleY(1);
          }
        }
      }
    }
  }
  .faq_aside {
    width: calc(33% - 29px);
    margin-left: 29px;
    .block_light {
      padding-top: 29px;
      padding-bottom: 29px;
    }
    .image_wrapper {
      width: 123px;
      margin-right: 29px;
      margin-top: 7px;
    }
    .description_wrapper {
      width: calc(100% - 152px);
      h3 {
        font-weight: 400;
        margin-bottom: 7px;
      }
      p {
        color: #777d97;
        margin-bottom: 21px;
      }
    }
  }
  @media screen and (max-width: 1600px){
    .faq_aside {
      width: 470px;
    }
    .faq_main {
      width: calc(100% - 499px);
    }
  }
  @media screen and (max-width: 1279px){
    .faq_aside {
      width: 100%;
      display: flex;
      margin-left: 0;
      align-items: flex-start;
      .block_light {
        width: calc(50% - 7px);
        &:first-of-type {
          margin-right: 14px;
        }
      }
    }
    .faq_main {
      width: 100%;
    }
  }
  @media screen and (max-width: 950px) {
    .faq_aside {
      display: block;
      .block_light {
        width: 100%;
        &:first-of-type {
          margin-right: 0;
        }
      }
    }
    .faq_main__list-item.open .inner {
      max-height: 400px;
    }
  }
  @media screen and (max-width: 520px) {
    .faq_wrapper {
      padding-left: 14px;
      padding-right: 14px;
    }
    .faq_main {
      h3 {
        padding-left: 14px;
        padding-right: 54px;
      }
      .icon {
        right: 14px;
      }
      .inner {
        padding-left: 29px;
        padding-right: 29px;
        ul li {
          padding-left: 14px;
        }
      }
    }
    .faq_aside {
      .block_light {
        flex-direction: column;
        padding-left: 14px;
        padding-right: 14px;
      }
      .image_wrapper {
        margin: 7px auto 14px;
      }
      .description_wrapper {
        width: 100%;
        h3 {
          text-align: center;
        }
        .btn {
          margin: 0 auto;
          display: block;
        }
      }
    }
    .faq_main__list-item.open .inner {
      max-height: 600px;
    }
  }
</style>

