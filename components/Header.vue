<template>
  <header class="p_header container container--justify wrapper">
    <button class="btn open-menu"
            onclick="document.querySelector('.mobile-nav').classList.toggle('open');
            document.querySelector('.p_header').classList.toggle('translated');
            document.querySelector('.p_container').classList.toggle('translated');">
      <span>Открыть меню</span>
      <svg
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              viewBox="0 0 45 31">
        <defs>
          <filter filterUnits="userSpaceOnUse" id="Filter_0" x="0px" y="0px" width="45px" height="31px"  >
            <feOffset in="SourceAlpha" dx="0" dy="6" />
            <feGaussianBlur result="blurOut" stdDeviation="2.646" />
            <feFlood flood-color="rgb(0, 0, 0)" result="floodOut" />
            <feComposite operator="atop" in="floodOut" in2="blurOut" />
            <feComponentTransfer><feFuncA type="linear" slope="0.25"/></feComponentTransfer>
            <feMerge>
              <feMergeNode/>
              <feMergeNode in="SourceGraphic"/>
            </feMerge>
          </filter>

        </defs>
        <g>
          <path fill-rule="evenodd"
                d="M6.000,10.000 L6.000,8.000 L38.000,8.000 L38.000,10.000 L6.000,10.000 ZM6.000,-0.000 L28.000,-0.000 L28.000,2.000 L6.000,2.000 L6.000,-0.000 ZM32.000,18.000 L6.000,18.000 L6.000,16.000 L32.000,16.000 L32.000,18.000 Z"/>
        </g>
      </svg>
    </button>
    <nav class="header_nav container">
      <h1 class="p_logo"><nuxt-link to="/">Waxcash</nuxt-link></h1>
      <ul class="container header_nav-list">
        <li><nuxt-link to='/'>Продажа</nuxt-link></li>
        <li><nuxt-link to='/shop'>Магазин</nuxt-link></li>
        <li><nuxt-link to='/'>Отзывы</nuxt-link></li>
        <li><button class="btn" type="button"
                    onclick="document.querySelector('.modals').classList.add('active');
                    document.querySelector('#modalHelp').classList.add('active');"
        >Помощь</button></li>
        <li class="glowing"><nuxt-link to='/referral'>Реферальная система</nuxt-link></li>
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
        <button class="btn"
                onclick="document.querySelector('.modals').classList.add('active');
                document.querySelector('#modalRefill').classList.add('active');"
        >Пополнить</button>
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
        <button class="btn open-profile-menu" type="button" onclick="this.classList.toggle('open')">
          <span class="angle">Открыть меню</span>
        </button>
        <ul class="profile_menu block_light">
          <li><nuxt-link to='/profile'>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 179.3 179.5">
              <title>profile</title>
              <path d="M3.4,176.1c-1.9-1.9-3.4-4.1-3.4-5s9.8-69,10.6-72a10.3,10.3,0,0,1,2.7-4.4c2.7-2.5,34-15.2,37.4-15.2s9.3,6,9.3,9.8c0,5.5-3.8,8.5-18,14.2-7.1,2.9-13,5.3-13,5.4l-3.5,23.9c-1.9,13-3.5,24.3-3.5,25.2s7.8,1.5,68,1.5c64.5,0,68-.1,68-1.8,0-4.1-6.9-47.5-7.7-48.1s-3.9-1.7-7.8-2.8l-17.4-5.4-10.5-3.2L105.1,89l-9.6-9.2-7.8-.6c-15-1.1-26.8-9-33.5-22.5-3.5-7.2-3.7-8.1-3.7-17.1s.3-10.2,3.2-16.3C58.1,14,63.7,8.2,72.8,3.7,80,.2,80.9,0,90,0s10,.2,17.2,3.7c9.1,4.5,14.7,10.3,19.1,19.6,2.9,6.1,3.2,7.6,3.2,16.2s-.3,10.1-3.1,16.1a54.5,54.5,0,0,1-7,10.8l-3.7,4.2,5.4,5.3c5.4,5.3,5.5,5.4,24.4,11.1,11.4,3.4,19.9,6.5,21.2,7.7s3,4,8.9,44.1c5.1,34.8,5.1,35.7-.5,39-2.7,1.6-9.7,1.7-85.6,1.7H6.8ZM101,56.1c5.9-3.9,8.5-8.9,8.5-16.6s-2.6-12.7-8.8-16.8-15.3-3.9-21-.3a20.7,20.7,0,0,0-8.8,22.9c1.4,5.1,7.5,11.7,12.3,13.1s13.5.6,17.8-2.3Z"/>
            </svg>
            Профиль</nuxt-link></li>
          <li><nuxt-link to='/accumulation'>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 160 200">
              <title>cards</title>
              <path d="M40.1,178.6C15.8,164.8,2.2,156.4,1.3,154.9A10.1,10.1,0,0,1,10.2,140c1.2,0,17.2,8.5,35.5,19S79.4,178,80,178s15.9-8.6,34.2-19,34.3-19,35.5-19c5.3,0,10.3,4.8,10.3,9.9s-1.7,6.8-40,28.6C98.8,190.6,81.3,200,79.9,200s-18.8-9.4-39.8-21.4Zm0-50C15.8,114.8,2.2,106.4,1.3,104.9A10.1,10.1,0,0,1,10.2,90c1.2,0,17.2,8.5,35.5,19S79.4,128,80,128s15.9-8.6,34.2-19,34.3-19,35.5-19c5.3,0,10.3,4.8,10.3,9.9s-1.7,6.8-40,28.6C98.8,140.6,81.3,150,79.9,150s-18.8-9.4-39.8-21.4Zm1.4-49.1C21.7,68.2,4.2,57.6,2.7,56q-5.4-6,0-12c4-4.3,42.5-26,46.2-26s9.2,4.6,9.3,9.2a11.6,11.6,0,0,1-1.5,6c-.9,1.4-7,5.6-13.7,9.3S31,49.6,31,50,78.6,78,80,78s49-27.2,49-28-12.8-7.9-28.4-16.8C72,16.9,70,15.3,70,10S74.9,0,80.2,0c3.1,0,73.6,40.3,77,44a10,10,0,0,1,2.8,6,10,10,0,0,1-2.8,6c-3.6,3.9-74,44-77.2,44-1.5,0-18.2-8.9-38.5-20.5Z"/>
            </svg>
            Накопления</nuxt-link></li>
          <li><nuxt-link to='/partnership'>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 160">
              <title>partnership_new</title>
              <path d="M3.4,156.6,0,153.2V27.3l2.9-3.9C6.2,19,21.2,4.1,25,1.6,27.2.2,34.4,0,100,0s72.8.2,75,1.6c3.8,2.5,18.8,17.4,22.1,21.8l2.9,3.9V153.2l-3.4,3.4-3.4,3.4h-28c-26.9,0-28-.1-30.6-2.1s-6.2-9.1-11.7-20L114,120H86l-2,4c-2.8,5.4-7.1,7.6-12.1,6.1-7.7-2.3-8.8-8.4-3.4-19S73.4,100,100,100c21.6,0,22.9.1,25.4,2.1s6.2,9.1,11.7,20L146,140h34V34.4l-7.3-7.2L165.5,20H34.4l-7.2,7.3L20,34.5V140H63.2l3.4,3.4c4.6,4.6,4.6,8.6,0,13.2L63.2,160H6.8Zm50-70c-3.2-3.2-3.4-3.8-3.4-10V70H43.4c-6.2,0-6.8-.2-10-3.4s-4.6-8.6,0-13.2,3.8-3.4,10-3.4H50V43.4c0-6.2.2-6.8,3.4-10S57.7,30,60,30s4.1,1,6.6,3.4,3.4,3.8,3.4,10V50h6.6c6.2,0,6.8.2,10,3.4s4.6,8.6,0,13.2S82.8,70,76.6,70H70v6.6c0,6.2-.2,6.8-3.4,10S62.3,90,60,90s-4.1-.9-6.6-3.4Zm80,0c-4.6-4.6-4.6-8.6,0-13.2,2.4-2.4,4.3-3.4,6.6-3.4,4.4,0,10,5.6,10,10s-5.6,10-10,10C137.7,90,135.8,89.1,133.4,86.6Zm-20-20c-4.6-4.6-4.6-8.6,0-13.2,2.4-2.4,4.3-3.4,6.6-3.4,4.4,0,10,5.6,10,10s-5.6,10-10,10C117.7,70,115.8,69.1,113.4,66.6Zm40,0c-4.6-4.6-4.6-8.6,0-13.2,2.4-2.4,4.3-3.4,6.6-3.4,4.4,0,10,5.6,10,10s-5.6,10-10,10C157.7,70,155.8,69.1,153.4,66.6Zm-20-20c-4.6-4.6-4.6-8.6,0-13.2,2.4-2.4,4.3-3.4,6.6-3.4,4.4,0,10,5.6,10,10s-5.6,10-10,10C137.7,50,135.8,49.1,133.4,46.6Z"/>
            </svg>
            Сотрудничество</nuxt-link></li>
          <li><nuxt-link to='/FAQ'>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 198.9 199.7">
              <title>faq</title>
              <path d="M93,196.1l-3.5-3.5V166.2l3.4-3.4c2.4-2.5,4.3-3.4,6.6-3.4s4.1.9,6.6,3.4,3.4,3.9,3.4,9.5,0,6.8,8,5c22.3-5,43.1-21.4,53.7-42.4a86.9,86.9,0,0,0,7.9-30.5C182.6,47.3,127,5.1,73.2,23.9A80.7,80.7,0,0,0,20.4,87.6c-1.4,8.6-.6,23.7,1.6,32.3,3.7,14.1,14.7,31.2,26.4,41,6.1,5.1,7,6.4,7,10.8a9.7,9.7,0,0,1-14.3,8.5c-4-2.1-11.9-9.3-17.5-16A105.7,105.7,0,0,1,1.8,120.9c-2.2-9.7-2.4-31.9-.4-41A102,102,0,0,1,80,1.3c7.7-1.7,31.2-1.7,39,0,39.7,8.7,69.8,38.9,78.6,78.6,1.7,7.8,1.7,31.2,0,39-9.9,44.9-46.6,76.9-91.8,80.1l-9.2.7Zm-.2-55.2-3.6-3.5.4-10.3c.3-8.7.8-11.1,3.2-15.9,3.2-6.6,7.5-10.7,15.6-14.8S119,88.2,119,79.3c0-5.4-.5-7.2-2.7-10.6-4.1-6.2-9-8.8-16.8-8.8-5.1,0-7.4.5-10.4,2.4a20.1,20.1,0,0,0-9.3,15.2c-.5,4.3-1.3,6.1-3.9,8.6-4.5,4.5-8.5,4.5-13.2-.2s-3.5-3.6-2.9-10.3c.8-8.8,6-19.4,12.2-25.2a52.4,52.4,0,0,1,11.3-7.3c6-2.9,7.6-3.2,16.2-3.2s10.1.3,16.1,3.2c9.3,4.4,15.1,10,19.6,19.1,3.6,7.2,3.8,8.1,3.8,17.1s-.3,10.2-3.2,16.2c-4.2,8.9-9.1,14.1-17,18s-9.3,6.3-9.3,16.4c0,7.4-.2,7.8-3.4,11.1s-8.6,4.6-13.3-.1Z"/>
            </svg>
            FAQ</nuxt-link></li>
          <li>
            <button class="btn open-socials" type="button" onclick="this.classList.toggle('show');">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1112.6 632.5">
                <title>vk</title>
                <path d="M885.4,630.6c-19.2-4.5-45.7-19.2-62.9-34.9-8.6-7.9-30.4-30.9-48.4-51-57.3-64.2-75.3-72.3-99.6-44.7-14.7,16.7-20.8,37.8-24.1,83.4-1.9,26.3-3.9,31.2-16.4,40.5-5.5,4.1-10.1,4.6-55.3,5.8-75.3,2.1-109.5-2.7-158.1-22.2-43.2-17.3-103.6-57.3-140.9-93.1-48.4-46.6-121.4-148-174.1-241.6C61.8,194.9,2.7,72.4.2,54.7c-1.3-9.8,3-17.3,13.1-22.8,6.4-3.5,15.8-3.9,96.1-4.6s90-.2,98.5,3c15.4,5.9,21.1,12.3,31.2,35.3,27.8,63.6,73.2,151.3,96.6,186.5,30.4,45.7,60.9,66.9,78.6,54.5,16-11.2,25.9-68.5,24-139.3C436.1,82,425.2,57.8,384,46.5c-8.3-2.3-13.7-5-14.1-7.1s3.6-7.5,8.7-12.5C400.8,5.1,426.9,0,516.3,0c99.8,0,121.1,5.9,131.8,36.7,2.5,7,3.1,31.3,3.1,124,0,113,.1,115.5,4.6,125.3,6.5,14,15.2,21.6,24.8,21.6,6.2,0,10.7-2.4,21.8-11.6,16.5-13.6,26.7-25.5,46.1-53.7,35.3-51.4,62.1-100,87.4-158.8,17.6-40.8,21.5-47.5,29.7-51.4,3.7-1.8,38-2.8,115.1-3.3l109.9-.8,9.1,4.9c18.3,9.8,17.2,31.5-3.5,72.7-16,31.6-41.7,69.5-98.9,145.4-28.4,37.7-54.7,74.8-58.5,82.4-8.1,16.5-8.5,30.1-1.3,44.4,2.9,5.7,25.9,30.3,61.6,65.7,58.8,58.4,74.4,75.9,95.5,107.8,13.7,20.6,19.6,40.1,16.4,54.2-2,8.8-12.4,18.5-23.7,21.9-14.7,4.5-184.8,7.1-201.9,3.2Z"/>
              </svg>
              Социальные сети <span class="angle"></span>
            </button>
            <ul class="profile_menu__socials container">
              <li><a href="#">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 261.7 213.2">
                  <title>twitter</title>
                  <path d="M74.2,213.1c-26.9-2-48.6-8.5-69.4-20.9L0,189.4l8.4.3a107.8,107.8,0,0,0,53.8-12A134.7,134.7,0,0,0,78,167.8l1.2-.9-4-.4c-15.4-1.3-30.2-10.1-39.1-23-2.7-4-6-10.3-6.6-12.8s-.3-1.3,1.9-.9c3.7.7,12.2.5,17.1-.4l4.6-.8L48,126.9A53.5,53.5,0,0,1,11.8,88.8c-1-4-2-13.5-1.3-13.5L13,76.4c4.8,2.5,14.8,5.1,19.3,5.1h1.9l-1.6-1.1c-3.2-2.3-11-10.6-13.3-14.2-8.9-14-11.1-31.7-5.6-46.9,1-3,3.5-8.5,4.1-9.1s1.1.8,2.1,2A173.8,173.8,0,0,0,37.1,29.3a151.8,151.8,0,0,0,85.3,36.3c3.3.3,6.2.5,6.3.3a13.2,13.2,0,0,0-.4-3.7c-.9-5.1-.3-16.9,1-21.8A53.1,53.1,0,0,1,144,15.5,50.2,50.2,0,0,1,161,4c19.6-7.9,41.5-4,56.6,10l3.1,2.9,3.8-.8a117.1,117.1,0,0,0,23.2-8.5c7.9-3.9,7.8-3.9,4.9,2.4a58,58,0,0,1-17.1,20.8,32.4,32.4,0,0,0-3.4,2.7c0,.2,8.2-1.3,12.3-2.3A145.4,145.4,0,0,0,261,25.8c1.2-.5,1.1-.3-2.6,4.6a128.1,128.1,0,0,1-18.2,18.8l-4.9,4,.2,3.7c.3,4.6-.6,17.7-1.7,25.1a165.5,165.5,0,0,1-19.2,55.3c-24.5,42.5-64.1,68.9-112.4,74.8-6.3.8-23,1.4-28,1Z"/>
                </svg> Твиттер
              </a></li>
              <li><a href="#">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1112.6 632.5">
                  <title>vk</title>
                  <path d="M885.4,630.6c-19.2-4.5-45.7-19.2-62.9-34.9-8.6-7.9-30.4-30.9-48.4-51-57.3-64.2-75.3-72.3-99.6-44.7-14.7,16.7-20.8,37.8-24.1,83.4-1.9,26.3-3.9,31.2-16.4,40.5-5.5,4.1-10.1,4.6-55.3,5.8-75.3,2.1-109.5-2.7-158.1-22.2-43.2-17.3-103.6-57.3-140.9-93.1-48.4-46.6-121.4-148-174.1-241.6C61.8,194.9,2.7,72.4.2,54.7c-1.3-9.8,3-17.3,13.1-22.8,6.4-3.5,15.8-3.9,96.1-4.6s90-.2,98.5,3c15.4,5.9,21.1,12.3,31.2,35.3,27.8,63.6,73.2,151.3,96.6,186.5,30.4,45.7,60.9,66.9,78.6,54.5,16-11.2,25.9-68.5,24-139.3C436.1,82,425.2,57.8,384,46.5c-8.3-2.3-13.7-5-14.1-7.1s3.6-7.5,8.7-12.5C400.8,5.1,426.9,0,516.3,0c99.8,0,121.1,5.9,131.8,36.7,2.5,7,3.1,31.3,3.1,124,0,113,.1,115.5,4.6,125.3,6.5,14,15.2,21.6,24.8,21.6,6.2,0,10.7-2.4,21.8-11.6,16.5-13.6,26.7-25.5,46.1-53.7,35.3-51.4,62.1-100,87.4-158.8,17.6-40.8,21.5-47.5,29.7-51.4,3.7-1.8,38-2.8,115.1-3.3l109.9-.8,9.1,4.9c18.3,9.8,17.2,31.5-3.5,72.7-16,31.6-41.7,69.5-98.9,145.4-28.4,37.7-54.7,74.8-58.5,82.4-8.1,16.5-8.5,30.1-1.3,44.4,2.9,5.7,25.9,30.3,61.6,65.7,58.8,58.4,74.4,75.9,95.5,107.8,13.7,20.6,19.6,40.1,16.4,54.2-2,8.8-12.4,18.5-23.7,21.9-14.7,4.5-184.8,7.1-201.9,3.2Z"/>
                </svg> Группа ВКонтакте
              </a></li>
              <li><a href="#">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 546.1 382.9">
                  <title>youtube-simple</title>
                  <path d="M183.8,382.6c-75.5-2.1-112.9-5-128-10.1S26.9,357.3,19.7,345C5.9,321.5,0,275.5,0,191.7,0,125.1,3.9,81.1,11.8,57.3c5.5-16.7,9.3-23,19.1-32.2A66.1,66.1,0,0,1,62.8,7.9C109.1-2.7,437.4-2.6,483.7,8a67.1,67.1,0,0,1,48.1,41.5c10,25.6,12.9,52,14.1,124.2,1.5,91.9-4.5,146.5-18.7,170.5-4.4,7.3-13.9,16.9-21.7,21.9-14.6,9.4-27.1,11.6-83.4,14.6C393.9,382.1,219,383.6,183.8,382.6Zm55.3-131.8,54.4-28.3c60.7-31.3,67.5-34.9,67.9-36.2s-17.7-10.7-39.8-22.3l-60-31.2-31.3-16.4c-6.5-3.3-12.2-6.1-12.8-6.1s-1,34-1,75.6.5,75.5,1.1,75.5S227.9,256.7,239.1,250.8Z"/>
                </svg> YouTube канал
              </a></li>
              <li><a href="#">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 219.6 179.6">
                  <title>mail</title>
                  <path d="M3.4,176.2,0,172.8V56.4L3.4,53c2.3-2.3,4.3-3.4,6.4-3.4s13.7,6.8,41.5,24.1l38.5,24,28.6-19c32-21.3,32.4-21.4,38.2-15.7,4,4.1,4.4,8,1.2,12.1s-64.4,44.5-67.7,44.5-12.6-5.9-61.8-36.8L20,77.6v82H180V58l-3.4-1.6a29.9,29.9,0,0,1-12.7-12.2l-2.4-4.6H26.8l-3.4-3.4c-2.5-2.4-3.4-4.3-3.4-6.6s.9-4.1,3.4-6.6l3.4-3.4H161.5L164,15c8.9-16.9,33.2-20.2,47-6.4s10.6,38.1-6.4,47.1L200,58.1V172.8l-3.4,3.4-3.4,3.4H6.8Zm191.5-138c4.7-2.5,6.3-8.3,3.7-13.4-3.5-6.7-13.7-6.7-17.2,0C176.7,33.9,185.8,42.9,194.9,38.2Z"/>
                </svg> Электронная почта
              </a></li>
            </ul>
          </li>
        </ul>
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
  import MobileNavigation from '~/components/MobileNavigation'

  export default {
      components: {
          MobileNavigation
      },
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
      ul {
        list-style-type: none;
        padding: 0;
        margin: 0;
        align-items: center;
        li {
          margin: 0 14px;
          a, .btn {
            text-decoration: none;
            color: #777d97;
            font-weight: 500;
            text-align: center;
            font-size: 16px;
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
          transform: translate(5px, -4px) rotate(45deg);
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
          bottom: 100px;
          overflow: hidden;
          opacity: 0;
          left: 0;
          right: 0;
          display: block;
          background: #272938;
          transition: all 0.3s ease-out;
          li {
            padding: 7px;
            align-items: center;
          }
        }
        &.open {
          .angle {
            transform: translate(5px, 0) rotate(-135deg);
          }
          ul {
            opacity: 1;
            top: 41px;
            bottom: auto;
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
    .open-profile-menu {
      position: relative;
      .angle {
        font-size: 0;
        line-height: 0;
        transform: translateY(-14px) rotate(45deg);
      }
      + .profile_menu {
        position: absolute;
        right: -500px;
        top: 80px;
        width: 310px;
        padding: 14px 0 19px;
        list-style-type: none;
        background: #1D1E28 linear-gradient(to right, #184e68, #57CA85) no-repeat center bottom;
        background-size: 100% 5px;
        li {
          padding: 0;
          margin: 0;
          a, .open-socials {
            display: flex;
            width: 100%;
            padding: 14px 29px;
            color: #777d97;
            align-items: center;
            text-decoration: none;
            white-space: nowrap;
            svg {
              margin-right: 14px;
              height: 20px;
              width: 20px;
              path {
                fill: #777d97;
              }
            }
            &.nuxt-link-active, &:hover, &:focus {
              background: #17171F linear-gradient(to top, #184e68, #57CA85) no-repeat left center;
              background-size: 3px 100%;
              color: #5499e8;
              svg path {
                fill: #5499e8;
              }
            }
            .angle {
              margin-left: auto;
              transform: translateY(-3px) rotate(45deg);
            }
          }
        }
      }
      &.open {
        .angle {
          transform: translateY(-10px) rotate(-135deg);
        }
        + .profile_menu {
          right: 0;
        }
      }
    }
    .open-socials {
      + .profile_menu__socials {
        padding-left: 34px;
        display: flex;
        flex-direction: column;
        list-style-type: none;
        background: #17171F;
        li {
          overflow: hidden;
          height: 0px;
          a {
            padding-top: 7px;
            padding-bottom: 7px;
            text-decoration: none;
            &:hover, &:focus {
              background: transparent;
            }
          }
        }
      }
      &:hover, &:focus {
        .angle {
          border-color: #5499e8;
        }
      }
      &.show {
        .angle {
          transform: translateY(3px) rotate(-135deg);
          border-color: #5499e8;
        }
        + .profile_menu__socials {
          padding-top: 14px;
          padding-bottom: 14px;
          li {
            height: 34px;
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
  .open-menu {
    display: none;
    margin: 20px 14px auto 0;
    width: 35px;
    min-width: 35px;
    span {
      font-size: 0;
      line-height: 0;
      position: absolute;
    }
    svg {
      height: 100%;
      width: 100%;
      path {
        fill: white;
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
      .open-profile-menu {
        + .profile_menu {

        }
        &.open {
          + .profile_menu {

          }
        }
      }
    }
  }

  @media screen and (max-width: 1024px) {
    .open-menu {
      display: block;
    }
    .p_header {
      .header_nav-list, .user_settings, .user_balance, .user_profile .info, .user_profile .angle {
        display: none;
      }
      nav.header_nav {
        margin-right: auto;
        min-width: auto;
        width: auto;
      }
      .user_login-button {
        margin-left: 14px;
        .btn-huge {
          flex-wrap: wrap;
          width: auto;
          svg {
            margin-left: 0;
          }
        }
      }
      .open-profile-menu + .profile_menu {
        display: none;
      }
    }
  }
  @media screen and (max-width: 340px) {
    .p_header {
      .user_login-button {
        .btn-huge {
          padding: 4px;
        }
      }
    }
  }
</style>

