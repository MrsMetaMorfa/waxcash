<template>
  <header class="p_header container container--justify wrapper">
    <nav class="header_nav container">
      <h1 class="p_logo"><nuxt-link to="/">Waxcash</nuxt-link></h1>
      <button class="btn open-menu" onclick="document.querySelector('.header_nav-list').classList.toggle('open'); this.classList.toggle('active');">
        <span>Открыть меню</span>
      </button>
      <ul class="container header_nav-list">
        <li><nuxt-link to='/'>Продажа</nuxt-link></li>
        <li><nuxt-link to='/'>Магазин</nuxt-link></li>
        <li><nuxt-link to='/'>Отзывы</nuxt-link></li>
        <li><nuxt-link to='/'>Помощь</nuxt-link></li>
        <li class="glowing"><nuxt-link to='/'>Реферальная система</nuxt-link></li>
      </ul>
    </nav>
    <div class="header_user container">
      <div class="user_settings container">
        <button class="btn user_currency container" onclick="this.classList.toggle('open')">
          USD <span class="angle"></span>
          <ul>
            <li>USD</li>
            <li>RUB</li>
          </ul>
        </button>
        <button class="btn user_language container" onclick="this.classList.toggle('open')">
          <img src="~assets/images/flag.png" alt=""> RUS <span class="angle"></span>
          <ul>
            <li><img src="~assets/images/flag.png" alt="">RUS</li>
            <li><img src="~assets/images/flag.png" alt="">ENG</li>
          </ul>
        </button>
      </div>
      <div class="user_balance container" v-show="loggedIn">
        <p>Баланс: <span class="sum">350.08 Р</span></p>
        <button class="btn">Пополнить</button>
      </div>
      <div class="user_profile container" v-show="loggedIn">
        <div class="avatar">
          <img src="~assets/images/avatar.jpg" alt="UserAvatar">
        </div>
        <div class="info">
          <p class="nickname">Verner2K</p>
          <button class="btn btn-logout">
            <img src="~assets/icons/exit.svg" alt="Выход">Выход
          </button>
        </div>
        <span class="angle"></span>
      </div>
      <div class="user_login-button" v-show="!(loggedIn)">
        <button class="btn btn-huge container">Войти через <img src="~assets/icons/opskins.svg" alt="OPSKINS"></button>
      </div>
    </div>
  </header>
</template>

<script>
  export default {
      name: 'UserInfo',
      props: {
          loggedIn: {
              type: Boolean,
              required: true
          }
      }
  }
</script>

<style lang="less">
  .btn {
    color: inherit;
    border: none;
    border-radius: 0;
    background: transparent;
    padding: 0;
    cursor: pointer;
  }
  .angle {
    display: inline-block;
    width: 10px;
    height: 10px;
    margin: 5px;
    border: solid #777D97;
    border-width: 0 1px 1px 0;
    transform: rotate(45deg);
  }

  .p_header {
    background: #1A1C27;
    position: fixed;
    height: 80px;
    padding: 14px 29px;
    top: 0;
    align-items: center;
    width: 100%;
    right: 0;
    left: 0;
    z-index: 500;
    nav {
      margin: auto 0;
      align-items: center;
      .p_logo {
        display: inline-block;
        font-family: Lato, sans-serif;
        a {
          color: white;
          font-size: 23px;
          display: inline-block;
          line-height: 1.4;
          font-weight: 700;
          text-transform: uppercase;
          text-decoration: none;
          padding: 0 14px;
        }
      }
      .open-menu {
        display: none;
        margin: auto 14px;
        width: 24px;
        height: 19px;
        span {
          font-size: 0;
          line-height: 0;
          background: white;
          width: 24px;
          display: block;
          height: 2px;
          transition: all 0.25s ease-in-out;
        }
        &:before, &:after {
          content: '';
          display: block;
          background: white;
          width: 24px;
          height: 2px;
          transition: all 0.25s ease-in-out;
        }
      }
      ul {
        list-style-type: none;
        padding: 0;
        margin: 0;
        align-items: center;
        li {
          margin: 0 14px;
          a {
            text-decoration: none;
            color: #777d97;
            font-weight: 500;
            text-align: center;
            &:hover {
              text-decoration: none;
              color: #5499e8;
            }
          }
          &.glowing {
            a {
              color: #38d75a;
              text-shadow: 0 0 16px #38d75a;
              &:hover {
                text-shadow: 0 0 32px #38d75a;
              }
            }
          }
        }
      }
    }
    .header_user {
      align-items: center;
    }
    .user_settings {
      align-items: center;
      .btn {
        font-size: 17px;
        display: inline-block;
        position: relative;
        padding: 6px;
        align-items: center;
        .angle {
          transform: translate(5px, -2px) rotate(45deg);
        }
        &.container {
          display: flex;
          margin-left: 14px;
          img {
            margin-right: 5px;
            display: block;
          }
          span {
            margin-left: 5px;
          }
        }
        ul {
          margin: 0;
          padding: 0;
          list-style-type: none;
          position: absolute;
          top: 41px;
          left: 0;
          display: none;
          li {
            padding: 6px;
          }
        }
        &.open {
          ul {
            display: block;
          }
        }
      }
      &:after {
        content: '';
        display: block;
        height: 41px;
        width: 1px;
        background: #292c3d;
        margin: 0 8px;
      }
    }
    .user_balance {
      margin: 0 14px;
      align-items: center;
      .sum {
        color: #38d75a;
        white-space: nowrap;
      }
      .btn {
        margin-left: 14px;
        padding: 14px;
        text-transform: uppercase;
        border-radius: 2px;
        background-color: rgb(39, 41, 56);
      }
      &:after {
        content: '';
        display: block;
        height: 41px;
        width: 1px;
        background: #292c3d;
        margin: 0 8px;
      }
    }
    .user_profile {
      .avatar {
        border-radius: 6px;
        overflow: hidden;
      }
      .info {
        margin-left: 14px;
        margin-right: 8px;
        .btn-logout {
          display: flex;
          align-items: center;
          color: #777d97;
          img {
            height: 20px;
          }
        }
      }
    }
  }
  .btn-huge {
    border-radius: 2px;
    background-color: rgb(56, 215, 90);
    padding: 14px;
    text-transform: uppercase;
    width: 222px;
    height: 41px;
    align-items: center;
    justify-content: center;
    img {
      margin-left: 14px;
      height: 21px;
    }
  }
  @media screen and (max-width: 1300px) {
    .p_header {
      nav .p_logo a {
      }
      nav {
        width: calc(100% - 600px);
        min-width: 420px;
        ul {
          width: calc(100% - 145px);
          height: 50px;
          flex-wrap: wrap;
          flex-direction: column;
          align-items: flex-start;
          justify-content: center;
          li {
            margin-top: auto;
            margin-bottom: auto;
            &:nth-of-type(odd) {
              margin-top: 0;
            }
            &:nth-of-type(even) {
              margin-bottom: 0;
            }
            &.glowing {
              margin-top: auto;
            }
          }
        }
      }
    }
  }
  @media screen and (max-width: 1200px) {
    .p_header {
      padding: 14px;
      nav .p_logo a {
        padding: 0;
      }
      nav {
        ul {
          li {
            margin-right: 0;
            &.glowing {
              width: 105px;
            }
          }
        }
      }
      .user_settings .btn.container:first-child {
        margin-left: 0;
      }
      .user_balance {
        margin: 0;
        p {
          display: inline-block;
          max-width: 90px;
        }
      }
    }
  }
  @media screen and (max-width: 1024px) {
    .p_header {
      nav {
        position: relative;
        min-width: 0;
        width: auto;
        .open-menu {
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          &.active {
            span {
              width: 0;
              margin: 0 auto;
              transition: all 0.25s ease-in-out;
            }
            &:before {
              transform-origin: left center;
              transform: rotate(45deg);
              transition: all 0.25s ease-in-out;
            }
            &:after {
              transform-origin: left center;
              transform: rotate(-45deg);
              transition: all 0.25s ease-in-out;
            }
          }
        }
        ul {
          position: absolute;
          top: -400px;
          left: 130px;
          height: auto;
          background: #272938;
          color: white;
          border-radius: 2px;
          min-width: 0;
          padding: 15px 0;
          width: 200px;
          opacity: 0;
          transition: top 0.4s ease-out, opacity 0.4s ease-out;
          li {
            width: 100%;
            margin-left: 0;
            a {
              width: 100%;
              display: block;
              padding: 14px;
            }
            &.glowing {
              width: 100%;
            }
          }
          &.open {
            top: 44px;
            opacity: 1;
          }
        }
      }
    }
  }
  @media screen and (max-width: 767px) {
    .p_header {
      flex-direction: column-reverse;
      height: 132px;
      align-items: flex-start;
      nav {
        margin-right: auto;
      }
      .header_user {
        margin-left: auto;
        flex-wrap: wrap;
        justify-content: flex-end;
      }
    }
  }
  @media screen and (max-width: 631px) {
    .p_header {
      flex-direction: row;
      position: relative;
      nav {
        margin-top: auto;
        margin-bottom: 0;
        min-width: 168px;
        position: absolute;
        bottom: 22px;
        ul {
          left: 0;
        }
      }
      .header_user {
        .user_profile {
          margin-top: 14px;
        }
      }
    }
  }
  @media screen and (max-width: 560px) {
    .p_header {
      position: relative;
      height: auto;
      flex-direction: column-reverse;
      nav {
        position: relative;
        bottom: 0;
        margin-top: 14px;
        margin-bottom: 5px;
      }
      .header_user {
        width: 100%;
        .user_settings, .user_balance, .user_login-button {
          margin: 0 auto 14px;
          &:after {
            display: none;
          }
        }
        .btn-huge {
          flex-wrap: wrap;
        }
        .user_profile {
          margin: 0;
          position: absolute;
          bottom: 14px;
          right: 14px;
        }
      }
    }
  }
  @media screen and (max-width: 360px) {
    .p_header {
      nav {
        width: 200px;
        margin-left: auto;
        justify-content: center;
        .p_logo {
          margin-left: 22px;
        }
      }
      .header_user {
        height: auto;
        .user_profile {
          position: relative;
          margin-top: 0;
          bottom: auto;
          right: auto;
        }
      }
    }
  }
</style>

