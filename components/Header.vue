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
          <ul class="block">
            <li>USD</li>
            <li>RUB</li>
          </ul>
        </button>
        <button class="btn user_language container" onclick="this.classList.toggle('open')">
          <img src="~assets/images/flag.png" alt=""> RUS <span class="angle"></span>
          <ul class="block">
            <li class="container"><img src="~assets/images/flag.png" alt="">RUS</li>
            <li class="container"><img src="~assets/images/flag.png" alt="">ENG</li>
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
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 472.6 386.1">
              <title>Exit</title>
              <path d="M71,384.8a75.3,75.3,0,0,1-24.1-8.4A88.6,88.6,0,0,1,2.1,320.5L0,312.7V73.4l2.1-7.9a90,90,0,0,1,62.6-63c7.1-2,9.1-2,63.4-2.4,62-.3,60.1-.5,63.2,5.5,1.2,2.3,1.4,5.2,1.2,14.7s-.6,12.2-2.2,14.4a10,10,0,0,1-4.2,3.2c-1.2.4-25.4.7-53.6.7-30.1.1-53.5.5-56.4,1.1-16.8,3.1-33.7,20-36.8,36.8-1.3,6.8-1.3,226.3,0,233.1,2.6,14.2,15.5,29.2,30.3,35.1,5.2,2.2,5.5,2.2,60.7,2.6,53,.5,55.5.6,58.3,2.3s4,4.4,4,17.9c.1,10.4-1.1,14.7-4.7,17.1-1.9,1.4-7.6,1.5-56.2,1.5-40-.1-55.8-.4-60.7-1.3Zm209.9-10.3a19.1,19.1,0,0,1-8.9-9.1c-1.6-3.5-1.7-7-1.7-49.2V270.7l-70-.2c-66.4-.3-70.2-.4-73.5-2s-9.7-8.4-10.6-12.6-.9-121.4,0-125.8,6-10.2,10.6-12.5,7.1-1.7,73.5-2l70-.2V70.1c0-48.8,0-49.1,4.9-54.3s16.6-7.7,23.8-3c2.2,1.4,41.8,40.4,87.8,86.6,88.4,88.6,85.8,85.7,85.8,93.6s2.6,5.1-85.8,93.7c-46,46.2-85.6,85.1-87.8,86.6s-5.1,2.7-9.7,2.6-6.8-.6-8.4-1.4Z"/>
            </svg>
            Выход
          </button>
        </div>
        <span class="angle"></span>
      </div>
      <div class="user_login-button" v-show="!(loggedIn)">
        <button class="btn btn-huge container" aria-label="Войти через OPSKINS"> Войти через
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 570.6 149.1">
            <title>OPSKINS</title>
            <path d="M45.6,144.8C25.8,134.2,8.9,120,3.1,108.9L0,103V19.3l4.3-3.2a109.8,109.8,0,0,1,26-13.4C37.5.2,39.3,0,53.1,0S69,.3,75.3,2.2c8.3,2.6,21.5,9.3,28.2,14.2l4.6,3.4v82.5l-2.3,4.8c-4.4,9.3-14.3,19.1-29,29-7.1,4.7-21.6,13-22.7,13a89.6,89.6,0,0,1-8.5-4.3Zm17.7-9.3C82.1,124.7,95,113.4,100,103.2l2.8-5.7.3-36.3.3-36.3L97.7,21C78.9,7.7,57.6,3,38.1,7.6c-8,1.9-22.3,8.7-28.7,13.6L4.8,24.7,5,61.6c.3,36.8.3,36.9,2.7,41.7s14.8,18,24.4,24.5c7,4.6,20.8,12.6,22,12.6s4.4-2.2,9.2-4.9Zm-14.5-9.3c-9.7-5.4-16.6-10.4-23.3-17.1C14.6,98.2,15,99.8,14.7,63.5l-.3-31.1,6.1-4.1c22-15,45.3-14.8,68.1.4l6.1,4.1-.3,30.9c-.3,30.3-.3,31-2.5,35.1-3,5.6-9.9,12.9-17.1,18.1s-18.9,12-20.2,11.9-3.2-1.2-5.8-2.6Zm8.2-31c0-3.7.1-3.8,4.3-4.9a19.7,19.7,0,0,0,8-4.4c3.3-3,3.6-3.7,3.6-8.6s-.4-5.7-2.8-8.2a29,29,0,0,0-8-5.1L57,61.9V50.4l3.6.6a60,60,0,0,1,6.1,1.2c2.2.5,2.6.1,4.1-3.6s1.5-4.2,1.3-4.3S60.4,41,58.7,41,57,40.2,57,38s-.3-2.9-2.7-2.6-2.7.9-3,2.9S50.4,41.1,47,42c-15.5,4.2-15.5,20.7,0,26.7l4.2,1.5v6.2c0,4.3-.4,6.1-1.2,6.1S41.6,80.6,36.4,79c-1.4-.5-1.6.1-1.6,3.9s.1,4.6,3.4,6a38.8,38.8,0,0,0,8.3,2l4.7.6v3.7c0,3.5.1,3.7,2.9,3.7s2.9-.2,2.9-3.7Zm0-17.5c0-5.2.7-5.9,3.2-3.1s2,5.5-.8,6.8S57,82.4,57,77.7ZM48.5,57.9c-2.7-1.9-2.8-4.9-.1-6.3s2.9-.9,2.6,3.8S50.7,59.4,48.5,57.9Zm100.1,43.6c-16.5-4.7-25.4-22.2-22.3-44.3,1.5-10.1,4.7-16.8,10.9-22.4s12.3-7.7,23-7.1c7.1.3,9.2.8,13.6,3.3,6.1,3.4,11.3,9.8,14,17,1.5,4.1,1.9,7.6,1.9,17.6,0,11.8-.2,13-2.7,18.5A32.6,32.6,0,0,1,171.4,100c-5.9,2.6-16.5,3.3-22.8,1.5Zm16.4-15c4.5-3.2,6.3-8.4,6.7-19.4s-.8-17.3-5.1-22.1c-3-3.2-3.7-3.5-8.7-3.5s-5.7.4-8.2,2.9c-8.2,8.2-7.4,37.5,1.2,42.1,5.4,2.9,9.9,2.9,14.1,0Zm120.5,15.3c-12.3-3.1-20.9-12.1-21-21.9,0-2.1.4-2.2,8.6-2.2h8.6l1.3,4.1c1.6,4.9,5.8,7.5,12.3,7.5,3.3,0,4.7-.6,7.1-2.9,5.3-5.4,1.9-10.5-9.7-14.5-14.5-5-21.1-9.6-24.3-16.7a16.2,16.2,0,0,1-.1-14.7c3.9-8.6,13.1-13,27-13,7.2,0,9.2.4,14.2,2.8s10,6.9,11.9,12.5,2.1,7-7.8,6.7-8.9-.4-9.5-2.6c-1.9-8.2-18.1-7.9-19.1.3-.5,4,2.8,6.8,12,10.2,20.1,7.2,26.3,13.8,25.3,26.5s-9.5,17.9-24.7,18.5A57.8,57.8,0,0,1,285.5,101.8Zm234.3,0c-10.3-2.5-18.8-10.9-20.3-20l-.6-4.1h9.3c8.7,0,9.3.1,9.3,2a9.7,9.7,0,0,0,5.9,8.5c10,3.5,19.2-2.2,15.2-9.5-1.6-2.8-4.9-4.7-16.1-8.8-8.8-3.3-14.9-7.5-18.3-12.4-1.7-2.6-2.2-4.6-2.2-9.7s.4-7,2.9-10.5c4.6-6.3,11.1-9.1,22.4-9.6s16.7,1,22.4,5.8c4.1,3.3,7.3,9.3,7.4,13.5v2.7h-8.5c-8.5,0-8.5,0-9.5-2.8-3.3-8.7-19.2-7.9-19.2.9,0,4.2,2.9,6.2,14.8,10.5,9.7,3.4,15,6.9,19.1,12.2,2.5,3.3,2.8,4.4,2.8,11.5s-.3,8.2-2.8,11.6c-4.2,5.5-11.4,8.4-21.7,8.8a60.8,60.8,0,0,1-12.3-.6ZM199.9,65.1V28.3l20,.3c22.3.4,24.2.9,30.8,7.7,9.8,10.2,8.3,27.7-2.8,35.3-5.6,3.7-11.8,5.1-22.5,5.1h-8.2v25.1H199.9ZM236.3,60c2.2-2.2,2.7-3.5,2.7-7.5s-.4-5.2-3.2-7.7S232.1,42,224.9,42h-7.7V63.4l8.2-.3c7.4-.3,8.4-.6,10.9-3.1Zm94.9,5.1V28.5h18.3V59.7l10.7-15.6,10.6-15.6H382c8.8,0,11,.2,10.2,1.2-10.8,14-23.4,30.6-23.4,31s5.4,9.4,12.1,20.3,12,20.1,12,20.4-4.6.4-10.4.4H372.1l-7.7-13.5-7.7-13.4-3.6,3.5-3.6,3.5v19.9H331.2Zm67.5,0V28.5h18.4v73.3H398.7Zm30,0V28.4l9.3.3,9.3.2,12.2,21.5c6.7,11.8,12.5,21.4,12.9,21.5s.7-9.8.7-21.7V28.5h17.4v73.3H472.6L460,79.6,447.5,57.5l-.3,22.2-.2,22.1H428.7V65.1ZM560.1,25a8.3,8.3,0,0,0-1.3-4.1c-.9-.9-.5-1.1,1.7-1.1s2.4.3,1.7.7-1.3,2.2-1.5,4.1-.4,3.3-.6.4Zm3.9-1.4c-.1-4,0-4.2,1.3-2.4a6.3,6.3,0,0,1,1.4,2.7c0,.4.5.5,1,.2s1,.1,1,.9c0,2.4-1.8,2.6-2.6.3l-.7-2.2-.7,2.5c-.5,1.9-.7,1.5-.7-2Zm5.3.8c-.4-1.7-.2-3.5.3-4s1,.3,1,3C570.6,28.3,570.1,28.6,569.3,24.4Z"/>
          </svg>
        </button>
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
          height: 0;
          overflow: hidden;
          opacity: 0;
          left: 0;
          right: 0;
          display: block;
          background: #272938;
          transition: all 0.3s ease-out;
          li {
            padding: 7px;
          }
        }
        &.open {
          .angle {
            transform: translate(5px, 0) rotate(-135deg);
          }
          ul {
            height: calc(34px * 2);
            opacity: 1;
            transition: all 0.3s ease-out;
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
        display: flex;
        flex-direction: column;
        .btn-logout {
          display: flex;
          align-items: center;
          color: #777d97;
          margin-top: auto;
          svg {
            height: 14px;
            margin-right: 5px;
            path {
              fill: #777d97;
            }
          }
        }
      }
    }
    .user_login-button {
      .btn-huge {
        padding: 8px 14px;
        line-height: 23px;
        svg {
          margin-left: 10px;
          height: 21px;
          margin-top: 2px;
          path {
            fill: white;
          }
        }
      }
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

