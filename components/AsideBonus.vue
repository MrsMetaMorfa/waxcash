<template>
  <div class="block aside_bonus">
    <div class="bonus_monets container container--justify">
      <img src="~assets/images/monets.png" alt="">
      <span class="sum">377</span>
      <span class="currency">USD</span>
    </div>
    <div class="container container--justify block-level">
      <p class="level">Level 3</p>
      <p class="level-full">377/400 USD</p>
      <div class="level-progress">
        <div class="progress-bar" style="width: 94.25%"></div>
      </div>
    </div>
    <div class="bonus_system">
      <p>Система бонусов</p>
      <ul>
        <li class="container">
          <img src="~assets/images/0.png" alt="Начинающий торгаш">
          <div class="bonus_description">
            <p><strong>Начинающий торгаш</strong>
              <br>Размер скидки <span>0%</span></p>
          </div>
        </li>
        <li class="container">
          <img src="~assets/images/1.png" alt="Юный трейдер">
          <div class="bonus_description">
            <p><strong>Юный трейдер</strong>
              <br>Размер скидки <span>0.5%</span></p>
          </div>
        </li>
        <li class="container">
          <img src="~assets/images/2.png" alt="Цифровой барыга">
          <div class="bonus_description">
            <p><strong>Цифровой барыга</strong>
              <br>Размер скидки <span>1%</span></p>
          </div>
        </li>
        <li class="container">
          <img src="~assets/images/3.png" alt="Прошареный парень">
          <div class="bonus_description">
            <p><strong>Прошареный парень</strong><br>Размер скидки <span>1.5%</span></p>
          </div>
        </li>
      </ul>
      <nuxt-link class="btn" to="/accumulation">ПОДРОБНЕЕ</nuxt-link>
    </div>
  </div>
</template>

<style lang="less">
  .block {
    border-radius: 2px;
    background-color: rgb(22, 23, 31);
    &:not(:last-of-type) {
      margin-bottom: 14px;
    }
  }
  .aside_bonus {
    width: 100%;
    padding: 29px;
    height: 50%;
    min-height: 570px;
  }
  .bonus_monets {
    align-items: center;
    border-radius: 2px;
    background-color: rgb(39, 41, 56);
    padding: 8px 14px 8px 8px;
    .sum {
      font-size: 20px;
      font-weight: 700;
      margin: auto 0;
      line-height: 20px;
    }
    .currency {
      color: #777d97;
      margin: auto 0;
      line-height: 20px;
    }
  }
  .block-level {
    padding: 14px 0;
    flex-wrap: wrap;
    p {
      width: 50%;
      &.level-full {
        text-align: right;
        font-size: 14px;
        color: #777d97;
      }
    }
    .level-progress {
      background-color: rgb(39, 41, 56);
      height: 6px;
      width: 100%;
      border-radius: 3px;
      position: relative;
      margin: 14px 0;
      .progress-bar {
        background: linear-gradient(to right, #b721ff, #21d4fd);
        position: absolute;
        left: 0;
        top: 0;
        height: 6px;
        border-radius: 3px;
        &:after {
          content: '';
          border-radius: 50%;
          background-color: rgb(255, 255, 255);
          position: absolute;
          width: 12px;
          height: 12px;
          display: block;
          right: 0;
          top: 0;
          margin-right: -3px;
          margin-top: -3px;
          box-shadow: 0 0 7px -1px white;
        }
      }
    }
  }
  .bonus_system {
    text-align: center;
    color: #777d97;
    p {
      margin-bottom: 14px;
    }
    ul {
      padding: 0;
      list-style-type: none;
      width: 100%;
      li {
        align-items: center;
        text-align: left;
        padding: 0 0 14px;
        p {
          font-size: 10px;
          margin-bottom: 0;
          strong {
            font-size: 16px;
            color: white;
          }
          span {
            color: #4d8cd5;
          }
        }
        img {
          width: 50px;
          margin-right: 14px;
        }
      }
    }
    .btn {
      width: 100%;
      color: #737992;
      background: rgb(39, 41, 56);
      border-radius: 2px;
      padding: 7px 14px;
      text-decoration: none;
      display: block;
      font-weight: 700;
    }
  }

  @media screen and (max-width: 1824px) {
    .aside_bonus {
      margin: 0 14px 0 0 !important;
      display: flex;
      flex-direction: column;
      height: 375px;
      min-height: 0;
      max-height: 500px;
      flex-wrap: wrap;
      justify-content: center;
      width: 75%;
      .bonus_monets, .block-level {
        width: calc(33%);
        margin-right: 29px;
      }
      .bonus_system {
        width: calc(66% - 29px);
        ul {
          display: flex;
          flex-wrap: wrap;
          li {
            width: 50%;
            min-width: 240px;
          }
        }
      }
    }
  }
  @media screen and (max-width: 1160px) {
    .aside_bonus {
      width: calc(67% - 29px);
      height: 428px;
      .bonus_monets, .block-level {
        width: calc(45%);
      }
      .bonus_monets {
        margin-top: auto;
      }
      .block-level {
        margin-bottom: auto;
      }
      .bonus_system {
        width: calc(55% - 29px);
        ul {
          li {
            width: 100%;
          }
        }
      }
    }
  }
  @media screen and (max-width: 900px) {
    .aside_bonus {
      width: 100%;
      margin: 0 0 14px!important;
      height: 320px;
      .bonus_system {
        width: 66%;
        ul {
          li {
            width: 50%;
            min-width: auto;
          }
        }
      }
      .bonus_monets, .block-level {
        width: calc(34% - 29px);
      }
    }
  }
  @media screen and (max-width: 767px) {
    .aside_bonus {
      height: auto;
      flex-direction: row;
      .bonus_system {
        width: 100%;
        ul {
          li {
            width: 50%;
            min-width: auto;
          }
        }
      }
      .bonus_monets, .block-level {
        width: calc(50% - 29px);
        margin: 0 auto 14px;
      }
    }
  }
  @media screen and (max-width: 530px) {
    .aside_bonus {
      max-height: none;
      .bonus_system {
        ul {
          li {
            width: 100%;
          }
        }
      }
      .bonus_monets, .block-level {
        width: 100%;
        margin: 0 auto 14px;
      }
    }
  }
</style>

