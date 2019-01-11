<template>
  <header class="p_header container container--justify wrapper">
    <nav class="header_nav container">
      <h1 class="p_logo"><nuxt-link to="/">Waxcash</nuxt-link></h1>
      <ul class="container">
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
      <div class="user_balance container">
        <p>Баланс: <span class="sum">350.08 Р</span></p>
        <button class="btn">Пополнить</button>
      </div>
      <div class="user_profile container">
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
      <!--<div class="user_login-button">-->
        <!--<button class="btn btn-huge container">Войти через <img src="~assets/icons/opskins.svg" alt="OPSKINS"></button>-->
      <!--</div>-->
    </div>
  </header>
</template>

<script>
  export default {
      name: 'UserInfo',
      props: {}
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
      ul {
        list-style-type: none;
        padding: 0;
        margin: 0;
        li {
          margin: 0 14px;
          a {
            text-decoration: none;
            color: #777d97;
            font-weight: 500;
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
          transform: translate(5px, -5px) rotate(45deg);
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
    .user_login-button {
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
    }
  }
</style>

