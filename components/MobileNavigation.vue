<template>
  <div class="mobile-nav">
    <div class="mobile-nav_wrapper block_light">
      <div class="user container">
        <div class="avatar" v-show="loggedIn">
          <img src="~assets/images/avatar.jpg" alt="UserAvatar">
        </div>
        <div class="info">
          <p class="nickname" v-show="loggedIn">Verner2K</p>
          <div class="user_settings container">
            <button class="btn user_currency container" onclick="this.classList.toggle('open')">
              USD <span>&#62;</span>
              <ul class="block">
                <li>USD</li>
                <li>RUB</li>
              </ul>
            </button>
            <button class="btn user_language container" onclick="this.classList.toggle('open')">
              <img src="~assets/images/flag.png" alt=""> RUS <span>&#62;</span>
              <ul class="block">
                <li class="container"><img src="~assets/images/flag.png" alt="">RUS</li>
                <li class="container"><img src="~assets/images/flag.png" alt="">ENG</li>
              </ul>
            </button>
          </div>
        </div>
        <button class="btn close-menu"
                onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                document.querySelector('.p_header').classList.toggle('translated');
                document.querySelector('.p_container').classList.toggle('translated');">
          <span>Закрыть меню</span>
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 180 159.9">
            <title>arrow</title>
            <path d="M74.9,158.2C70.9,155.6,3,87.6,1.4,84.7-.9,80.3-.4,77,3.4,73.3l3.4-3.4H173.2l3.4,3.4c4.6,4.6,4.6,8.6,0,13.2l-3.4,3.4H34.5l26.1,26.2c14.3,14.5,26.8,27.4,27.7,28.8,2.7,4,2.1,7.8-1.7,11.6S78.9,160.9,74.9,158.2ZM29.8,58.2A9.3,9.3,0,0,1,26.6,45C28.9,41.3,73.6,1.9,76.9.6c8.9-3.3,16.8,7.9,10.8,15.3-2.2,2.8-46.2,41.6-48.4,42.8a9.3,9.3,0,0,1-9.5-.5Z"/>
          </svg>
        </button>
      </div>
      <div class="balance container" v-show="loggedIn">
        <svg class="balance_wallet" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 975 975.2">
          <defs>
            <linearGradient id="a" x1="-110.52" y1="698.44" x2="219.83" y2="985.7"
                            gradientTransform="matrix(2.83, 0, 0, -2.83, 306.48, 2783.7)"
                            gradientUnits="userSpaceOnUse">
              <stop offset="0" stop-color="#184e68"/>
              <stop offset="1" stop-color="#57ca85"/>
            </linearGradient>
          </defs>
          <title>Green wallet</title>
          <path class="a" d="M436.5,837.8c-29.1-2.5-55.4-13.7-81.7-35C332.7,785.1,53.9,503.9,44.2,489.7,27.4,465,19.4,441.4,17.5,411.3a147.7,147.7,0,0,1,24.9-92.7c6.7-10,49.4-54.3,148-153.5C347.9,6.6,338.1,14.9,369.2,14.9c27.3,0,31.7,2.9,82.9,53.7l43.4,42.9,39.1-38.8c35.4-34.9,40.3-39.2,50.9-43.1,16.9-6.3,36.3-6,51.5.9,9.4,4.2,17.8,11.5,48.3,42l36.8,36.9,7.1-3.1c4.5-2,12.9-3.2,22.7-3.2,25.4-.1,30.3,3.1,76.4,49.5,25.3,25.6,40.8,42.7,43.8,48.7,6.4,12.6,7.9,33.7,3.3,47.7l-3.3,10.2,36.2,36.4c43.2,43.3,47.3,49.9,47.3,75.6,0,30.3,13.4,15.1-211.9,240C586.4,768.3,541.9,811.7,532.6,817c-31,17.8-59.5,24-96.1,20.8Z"/>
          <path class="b" d="M274.4,972.4c-13.6-7.6-13.2-29.1.7-35.4,4-1.8,56.6-2.4,213.9-2.4H697.6l6.9,6.9c5,5,7,8.7,7,13.4s-2,8.4-7,13.4l-6.9,6.9H488.4c-169.7-.1-210.1-.6-214-2.8ZM435.7,855c-30.3-2.7-57.6-14.4-85-36.4C327.8,800.2,38.1,508.1,28.1,493.3,10.7,467.6,2.3,443.2.3,411.9a154,154,0,0,1,25.9-96.3c6.9-10.4,51.4-56.5,153.8-159.5C343.6-8.5,333.4.1,365.7.1c28.4,0,32.9,2.9,86.2,55.7l45,44.6,40.7-40.2c36.7-36.4,41.8-40.8,52.8-44.9,17.6-6.5,37.7-6.1,53.5.9,9.8,4.4,18.5,12,50.2,43.7l38.2,38.3,7.4-3.2c4.6-2,13.4-3.3,23.6-3.3,26.3-.1,31.4,3.2,79.3,51.5,26.3,26.5,42.4,44.3,45.6,50.5,6.6,13.1,8.1,35,3.4,49.6l-3.5,10.5,37.7,37.8c44.8,45.1,49,51.9,49,78.6,0,31.5,14,15.7-220,249.4C591.3,782.7,545.1,827.7,535.4,833.3c-32.1,18.5-61.8,24.9-99.7,21.7Zm44.9-42.8c5.6-1.2,17-5.4,25.4-9.3,15-7,19.2-11,220.3-211.8,219-218.7,211.1-210.1,208-227.4-1.3-6.6-6.7-13.1-36.3-42.9-19.2-19.3-35.8-35-37-35s-8.1,5.9-15.3,13.2l-13.1,13.2,22.7,22.9c12.5,12.6,23.7,25.5,24.9,28.7,4.1,10.8-.2,16.9-37.2,53.7-33,32.9-35.7,35-42.8,35-9.8,0-14.7-2.7-18.6-10.1-6.4-12.4-4.9-15.1,23.4-43.7,14.6-14.7,26.5-27.6,26.5-28.7s-6-7.9-13.2-15l-13.2-13.1-33.5,33c-40.7,40.1-47.6,44.1-74.4,44s-30.5-2.6-78.5-50.6-50.7-51.7-50.6-80.5c0-26.6,2.3-30.4,43.3-71.7l33.9-34-14.1-14.3-14.1-14.2L590.2,180c-26.1,25.8-27,26.4-35.7,26.4-10.5-.1-17.3-4.7-19.6-13.2-3.2-12.2-1-15.3,36-52.4s36.1-36.1,44.9-36.1,9.6.8,32.5,23.4c13,12.9,24.6,23.4,25.7,23.4s7.9-5.9,15.1-13.2L702.2,125,666.7,89.4C628,50.7,624,48.1,608.8,52c-7.2,1.9-33.8,27.7-210.6,204.2C253.2,401,193.3,459.6,186.7,462.8c-13.6,6.9-36.1,7.7-51.1,2.1a67.7,67.7,0,0,1-36.2-33.1c-5.5-10.9-6.3-14.6-6.3-29.1,0-29.1-1.7-26.8,109.3-137.8,96.2-96,97.4-97.1,105.5-97.1,12.9,0,22.8,11.8,19.9,24-.8,3.6-34.1,38.5-97.4,102.1-103.3,103.9-101.3,101.4-96,117.4,3.4,10.2,13.4,16.8,25.6,16.8h9.4l149-148.9,149-149L425.2,87.8C402,64.5,380.5,44.2,377.5,42.6a25.9,25.9,0,0,0-23.6,0c-3,1.6-70.2,67.7-149.2,146.9L61,333.5l-8.2,17.3c-16.7,35.3-16.8,67.9-.2,103.5l8,17,153,153.8c84.1,84.7,158.4,158.3,165,163.6,29.9,24.4,62.9,32,102,23.5Zm53.7-115.4c-4.4-4.5-5.9-7.9-5.9-13.7,0-7.3,2-9.8,37.2-44.9S603.3,601,610.2,601c14.6,0,24.6,14.4,18.9,27.5-1.4,3.3-18.1,21.4-37,40.1-33.8,33.4-34.7,34.1-43.1,34.1C542.1,702.7,539.1,701.5,534.3,696.8ZM665.4,576.6c-6.6-2.7-10.9-10.2-10.9-19.1s1.5-9.6,35.9-44.2c24.7-24.9,37.8-36.6,41.9-37.5,12.7-2.8,23.9,7.4,23.9,21.7,0,5.8-4.1,10.8-34.1,41C682,578.9,677.9,581.7,665.4,576.6ZM293.2,454.7c-7.6-4.6-12-15.5-9.1-22.7,1-2.7,18.3-21.1,38.3-41,28.7-28.5,37.6-36.1,41.8-36.1,16.6,0,26.5,15.7,18.9,30.1-3.5,6.6-65.3,68.2-71.7,71.4S300.5,459.2,293.2,454.7ZM415.9,328.4c-7.3-5.7-9.2-16.8-4.5-25.6,2-3.6,18.4-21.2,36.4-39,35.1-34.6,39.1-37.1,51.7-31.8,7.9,3.3,12.8,13.2,11.1,22.2-.8,4.4-10.3,15.4-33.9,39.4-18,18.2-35.2,34.5-38.2,36.1-7.8,4-16.5,3.5-22.6-1.3ZM347.4,157.1c-2.8-1.4-6.7-5.9-8.8-10-3.2-6.7-3.3-8.2-.7-14.2,3.5-8.2,14.5-19,22.2-21.9,10.3-3.9,22.9,3.8,25.1,15.2,1.3,7.4-1.1,13.3-9.1,21.9-10,10.8-19.2,13.7-28.7,9ZM781.9,305.8l71.9-72v-22l-37.1-37.4c-20.4-20.6-39.6-38.7-42.6-40.3a22.4,22.4,0,0,0-21.6,0c-3,1.6-36.4,33.9-74.2,71.8-73.5,73.6-74.1,74.5-70.1,89.9,1.4,5.2,10.5,15.8,33.8,39.4,41,41.7,45,44.8,58,43.6l9.9-1,72-72ZM682,331.3c-34.7-12.7-39.9-61.1-8.8-81.6,7.5-5,10.3-5.6,25-5.6s17.6.6,25,5.5c24.2,16,27.4,50.1,6.7,70.8C716.2,334,699.7,337.8,682,331.3Z"/>
        </svg>
        <div class="balance_info">
          <p>Ваш баланс:</p>
          <p><span class="sum">350.08</span> Рублей</p>
        </div>
        <button class="btn btn-dark"
                onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                document.querySelector('.p_header').classList.toggle('translated');
                document.querySelector('.p_container').classList.toggle('translated');
                document.querySelector('.modals').classList.add('active');
                document.querySelector('#modalRefill').classList.add('active');"
        >
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 199.5 199.2">
            <title>Пополнить</title>
            <path d="M162.4,177.7l-7.1,5c-23.4,16.2-57.4,21-85.4,12-17.8-5.8-27.1-11.5-40.6-25.1C17.4,157.8,11.8,149,6.4,134.2-.8,114.1-1.9,96,3,76c2.1-8.8,4.9-11.8,10.6-11.8,3.2,0,4.8.6,6.9,2.7s3.6,5.5,1.7,14.5c-2.4,11-2.8,17.9-1.7,27.4a79.5,79.5,0,0,0,19.6,43.7c37.7,42.8,107,33.3,131.8-18,19.1-39.8,2.4-87.7-37.2-106.8-29.8-14.3-67.5-8.4-90.2,14.2-2.9,3-4.1,3.5-8.2,3.5-6.6,0-9.4-2.8-9.4-9.6v-5l7-6c34.3-29.7,82.9-33,121.6-8.3,6.7,4.3,23.3,20.9,27.6,27.6,21.4,33.5,21.9,75.3,1.3,108.9-3.4,5.7-17.9,21.9-22,24.7ZM99.9,151.4c-5.4,0-8.5-2.3-9.5-6.9-.3-1.6-.6-10.1-.7-18.8V109.9H73.8c-18.1-.1-20.8-.5-23.6-3.3s-2.8-10.9,0-13.7,5.5-3.2,23.6-3.3H89.6V73.6c.1-8.7.4-17.1.7-18.7,1-4.7,4.1-7,9.5-7s8.5,2.3,9.5,7,1,81.9.2,87.6-3.6,8.9-9.7,8.9Zm42.8-42c-9.6,1.4-18.7.2-21.8-2.9s-2.8-10.9,0-13.7,9-3.7,16.3-3.4c11.2.5,14.5,2.8,14.5,10.3s-2.5,8.7-9,9.7Z"/>
          </svg>
          Пополнить</button>
      </div>
      <nav class="nav" :class="{'big' : !loggedIn}">
        <vue-scroll :ops="ops">
          <div class="scroll-wrapper">
            <ul class="nav-list">
              <li><nuxt-link to='/index-loggedin'
                             onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                             document.querySelector('.p_header').classList.toggle('translated');
                             document.querySelector('.p_container').classList.toggle('translated');">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 160">
                  <title>card</title>
                  <path d="M3.4,156.6,0,153.2V6.8L3.4,3.4,6.8,0H193.2l3.4,3.4L200,6.8V153.2l-3.4,3.4-3.4,3.4H6.8ZM180,80V20H20V40H153.2l3.4,3.4c4.6,4.6,4.6,8.6,0,13.2L153.2,60H20v80H180ZM43.4,116.6c-4.6-4.6-4.6-8.6,0-13.2l3.4-3.4H73.2l3.4,3.4c4.6,4.6,4.6,8.6,0,13.2L73.2,120H46.8Zm50,0c-4.6-4.6-4.6-8.6,0-13.2S97,100,105,100s8.3.1,11.6,3.4,3.4,4.3,3.4,6.6-1,4.2-3.4,6.6S113,120,105,120,96.7,119.9,93.4,116.6Z"/>
                </svg>
                Продажа</nuxt-link></li>
              <li><nuxt-link to='/shop'
                             onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                             document.querySelector('.p_header').classList.toggle('translated');
                             document.querySelector('.p_container').classList.toggle('translated');">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 199.5 199.8">
                  <title>cart</title>
                  <path d="M20.5,198.3C-.6,190.7-6.7,164.7,9,149c5.8-5.8,11.9-8.4,20-8.4a47.8,47.8,0,0,1,10.2.8l3.7.8,3.3-6.6,3.3-6.7L35.9,74.7,22.4,20.5,14.1,20c-7.8-.5-8.4-.7-11.2-3.8S-1,7.8,3.4,3.4L6.8,0H33.2l3.2,3.2c2.8,3,3.7,5.5,8.5,25L50.2,50h71c64.9,0,71.2.1,73.9,1.7,5.7,3.4,5.7,4.6-.2,34.6-5.1,25.7-5.5,27.4-8.4,30.2s-6.3,3.8-45.1,13.4-42.4,10.4-45,9.2c-7.5-3-8.4-13.4-1.6-17.3,1.5-.8,19.4-5.7,39.8-10.7l37-9.2,2.9-14.7c1.5-8.1,3-15.3,3.3-16S165.5,70,116.7,70H55.3l7.6,30.5,7.6,30.6-6.6,13-6.6,13.1,1.4,4.7c3,9.7-.1,21.5-7.7,29.1s-20.3,10.9-30.5,7.3Zm14.4-19.7c6.7-3.5,6.5-14.3-.4-17.4-5.1-2.3-10.7-.7-13.1,3.9C16.7,174.2,25.8,183.3,34.9,178.6Zm125.6,19.7c-21.1-7.6-27.2-33.6-11.5-49.3,6.1-6.1,11.9-8.5,21-8.5s14.9,2.4,21,8.5,8.5,11.9,8.5,21-2.4,14.9-8.5,21C183.1,199,170.7,201.9,160.5,198.3Zm14.4-19.7c6.7-3.5,6.5-14.3-.4-17.4-9-4.1-17.9,5.1-13.1,13.7C164,179.6,169.8,181.2,174.9,178.6Z"/>
                </svg>
                Магазин</nuxt-link></li>
              <li><nuxt-link to='/accumulation'
                             onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                             document.querySelector('.p_header').classList.toggle('translated');
                             document.querySelector('.p_container').classList.toggle('translated');">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 160 200">
                  <title>cards</title>
                  <path d="M40.1,178.6C15.8,164.8,2.2,156.4,1.3,154.9A10.1,10.1,0,0,1,10.2,140c1.2,0,17.2,8.5,35.5,19S79.4,178,80,178s15.9-8.6,34.2-19,34.3-19,35.5-19c5.3,0,10.3,4.8,10.3,9.9s-1.7,6.8-40,28.6C98.8,190.6,81.3,200,79.9,200s-18.8-9.4-39.8-21.4Zm0-50C15.8,114.8,2.2,106.4,1.3,104.9A10.1,10.1,0,0,1,10.2,90c1.2,0,17.2,8.5,35.5,19S79.4,128,80,128s15.9-8.6,34.2-19,34.3-19,35.5-19c5.3,0,10.3,4.8,10.3,9.9s-1.7,6.8-40,28.6C98.8,140.6,81.3,150,79.9,150s-18.8-9.4-39.8-21.4Zm1.4-49.1C21.7,68.2,4.2,57.6,2.7,56q-5.4-6,0-12c4-4.3,42.5-26,46.2-26s9.2,4.6,9.3,9.2a11.6,11.6,0,0,1-1.5,6c-.9,1.4-7,5.6-13.7,9.3S31,49.6,31,50,78.6,78,80,78s49-27.2,49-28-12.8-7.9-28.4-16.8C72,16.9,70,15.3,70,10S74.9,0,80.2,0c3.1,0,73.6,40.3,77,44a10,10,0,0,1,2.8,6,10,10,0,0,1-2.8,6c-3.6,3.9-74,44-77.2,44-1.5,0-18.2-8.9-38.5-20.5Z"/>
                </svg>
                Накопления</nuxt-link></li>
              <li><nuxt-link to='/profile'
                             onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                             document.querySelector('.p_header').classList.toggle('translated');
                             document.querySelector('.p_container').classList.toggle('translated');">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 179.3 179.5">
                  <title>profile</title>
                  <path d="M3.4,176.1c-1.9-1.9-3.4-4.1-3.4-5s9.8-69,10.6-72a10.3,10.3,0,0,1,2.7-4.4c2.7-2.5,34-15.2,37.4-15.2s9.3,6,9.3,9.8c0,5.5-3.8,8.5-18,14.2-7.1,2.9-13,5.3-13,5.4l-3.5,23.9c-1.9,13-3.5,24.3-3.5,25.2s7.8,1.5,68,1.5c64.5,0,68-.1,68-1.8,0-4.1-6.9-47.5-7.7-48.1s-3.9-1.7-7.8-2.8l-17.4-5.4-10.5-3.2L105.1,89l-9.6-9.2-7.8-.6c-15-1.1-26.8-9-33.5-22.5-3.5-7.2-3.7-8.1-3.7-17.1s.3-10.2,3.2-16.3C58.1,14,63.7,8.2,72.8,3.7,80,.2,80.9,0,90,0s10,.2,17.2,3.7c9.1,4.5,14.7,10.3,19.1,19.6,2.9,6.1,3.2,7.6,3.2,16.2s-.3,10.1-3.1,16.1a54.5,54.5,0,0,1-7,10.8l-3.7,4.2,5.4,5.3c5.4,5.3,5.5,5.4,24.4,11.1,11.4,3.4,19.9,6.5,21.2,7.7s3,4,8.9,44.1c5.1,34.8,5.1,35.7-.5,39-2.7,1.6-9.7,1.7-85.6,1.7H6.8ZM101,56.1c5.9-3.9,8.5-8.9,8.5-16.6s-2.6-12.7-8.8-16.8-15.3-3.9-21-.3a20.7,20.7,0,0,0-8.8,22.9c1.4,5.1,7.5,11.7,12.3,13.1s13.5.6,17.8-2.3Z"/>
                </svg>
                Профиль</nuxt-link></li>
              <li><nuxt-link to='/partnership'
                             onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                             document.querySelector('.p_header').classList.toggle('translated');
                             document.querySelector('.p_container').classList.toggle('translated');">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 160">
                  <title>partnership_new</title>
                  <path d="M3.4,156.6,0,153.2V27.3l2.9-3.9C6.2,19,21.2,4.1,25,1.6,27.2.2,34.4,0,100,0s72.8.2,75,1.6c3.8,2.5,18.8,17.4,22.1,21.8l2.9,3.9V153.2l-3.4,3.4-3.4,3.4h-28c-26.9,0-28-.1-30.6-2.1s-6.2-9.1-11.7-20L114,120H86l-2,4c-2.8,5.4-7.1,7.6-12.1,6.1-7.7-2.3-8.8-8.4-3.4-19S73.4,100,100,100c21.6,0,22.9.1,25.4,2.1s6.2,9.1,11.7,20L146,140h34V34.4l-7.3-7.2L165.5,20H34.4l-7.2,7.3L20,34.5V140H63.2l3.4,3.4c4.6,4.6,4.6,8.6,0,13.2L63.2,160H6.8Zm50-70c-3.2-3.2-3.4-3.8-3.4-10V70H43.4c-6.2,0-6.8-.2-10-3.4s-4.6-8.6,0-13.2,3.8-3.4,10-3.4H50V43.4c0-6.2.2-6.8,3.4-10S57.7,30,60,30s4.1,1,6.6,3.4,3.4,3.8,3.4,10V50h6.6c6.2,0,6.8.2,10,3.4s4.6,8.6,0,13.2S82.8,70,76.6,70H70v6.6c0,6.2-.2,6.8-3.4,10S62.3,90,60,90s-4.1-.9-6.6-3.4Zm80,0c-4.6-4.6-4.6-8.6,0-13.2,2.4-2.4,4.3-3.4,6.6-3.4,4.4,0,10,5.6,10,10s-5.6,10-10,10C137.7,90,135.8,89.1,133.4,86.6Zm-20-20c-4.6-4.6-4.6-8.6,0-13.2,2.4-2.4,4.3-3.4,6.6-3.4,4.4,0,10,5.6,10,10s-5.6,10-10,10C117.7,70,115.8,69.1,113.4,66.6Zm40,0c-4.6-4.6-4.6-8.6,0-13.2,2.4-2.4,4.3-3.4,6.6-3.4,4.4,0,10,5.6,10,10s-5.6,10-10,10C157.7,70,155.8,69.1,153.4,66.6Zm-20-20c-4.6-4.6-4.6-8.6,0-13.2,2.4-2.4,4.3-3.4,6.6-3.4,4.4,0,10,5.6,10,10s-5.6,10-10,10C137.7,50,135.8,49.1,133.4,46.6Z"/>
                </svg>
                Сотрудничество</nuxt-link></li>
              <li><nuxt-link to='/referral'
                             onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                             document.querySelector('.p_header').classList.toggle('translated');
                             document.querySelector('.p_container').classList.toggle('translated');">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 199.8 199.8">
                  <title>referral</title>
                  <path d="M93.3,197c-2.2-1.6-9.7-8.7-16.7-15.9-12.2-12.5-12.7-13.2-12.7-17.2a9.6,9.6,0,0,1,10-10c3.9,0,4.7.6,15.1,10.6l10.9,10.7,10.9-10.6,10.9-10.7,15.8-.2,15.9-.3.3-15.9.2-15.8,10.7-10.9,10.6-10.9L164.6,89,153.9,78.1l-.2-15.9-.3-15.8-15.9-.3-15.8-.3L110.8,35.2,99.9,24.6,89,35.2,78.1,45.8l-15.9.3-15.8.3-.3,15.8-.3,15.9L35.2,89,24.6,99.9l10.6,10.9,10.7,10.9v45.9l-2.5,2.5a9.6,9.6,0,0,1-11.3,2.2c-5.3-2.2-6.2-5.8-6.2-25.1V130.5L13.4,117.9C.9,105.1-.9,102.2.3,97.2.7,95.7,6.4,89,13.4,81.9L25.9,69.2V52.5c0-26.4.2-26.6,26.6-26.6H69.2L81.9,13.4C94.6.9,97.6-.9,102.5.3c1.5.4,8.2,6.1,15.4,13.1l12.6,12.5h16.7c26.4,0,26.7.2,26.7,26.6V69.2l12.4,12.7c7,7.1,12.8,13.8,13.1,15.3,1.3,5-.6,7.9-13.1,20.7l-12.4,12.6v16.7c0,26.5-.2,26.7-26.8,26.7H130.3L120.4,184c-16.7,16.8-19.8,18.4-27.1,13Zm25-65.5c-4.6-4.6-4.6-8.6,0-13.2,2.4-2.5,4.3-3.4,6.6-3.4s4.1.9,6.6,3.4c4.6,4.6,4.6,8.6,0,13.2-2.5,2.4-4.3,3.4-6.6,3.4S120.7,133.9,118.3,131.5Zm-45-5c-4.3-4.3-4.5-7.9-.5-13.2s38.4-39.4,42.1-41.8,7.8-2,11.6,1.8,4.4,7.6,1.7,11.6S91,123.6,86.5,127s-8.9,3.8-13.2-.5Zm-5-45c-4.6-4.6-4.6-8.6,0-13.2,2.4-2.5,4.3-3.4,6.6-3.4,4.4,0,10,5.5,10,10,0,2.3-1,4.1-3.4,6.6s-4.3,3.4-6.6,3.4-4.2-1-6.6-3.4Z"/>
                </svg>
                Реферальная система</nuxt-link></li>
              <li><button class="btn" type="button"
                          onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                          document.querySelector('.p_header').classList.toggle('translated');
                          document.querySelector('.p_container').classList.toggle('translated');
                          document.querySelector('.modals').classList.add('active');
                          document.querySelector('#modalHelp').classList.add('active');">
                  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 219.6 179.6">
                      <title>mail</title>
                      <path d="M3.4,176.2,0,172.8V56.4L3.4,53c2.3-2.3,4.3-3.4,6.4-3.4s13.7,6.8,41.5,24.1l38.5,24,28.6-19c32-21.3,32.4-21.4,38.2-15.7,4,4.1,4.4,8,1.2,12.1s-64.4,44.5-67.7,44.5-12.6-5.9-61.8-36.8L20,77.6v82H180V58l-3.4-1.6a29.9,29.9,0,0,1-12.7-12.2l-2.4-4.6H26.8l-3.4-3.4c-2.5-2.4-3.4-4.3-3.4-6.6s.9-4.1,3.4-6.6l3.4-3.4H161.5L164,15c8.9-16.9,33.2-20.2,47-6.4s10.6,38.1-6.4,47.1L200,58.1V172.8l-3.4,3.4-3.4,3.4H6.8Zm191.5-138c4.7-2.5,6.3-8.3,3.7-13.4-3.5-6.7-13.7-6.7-17.2,0C176.7,33.9,185.8,42.9,194.9,38.2Z"/>
                  </svg>
                  Помощь
              </button></li>
              <li><a href='#' class="btn"
                             onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                             document.querySelector('.p_header').classList.toggle('translated');
                             document.querySelector('.p_container').classList.toggle('translated');">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 189.6 180">
                  <title>hand_like</title>
                  <path d="M63,176.6c-4.3-4.4-4.5-8.3-.5-12.8l3-3.3,43.7-.5,43.8-.5,8.3-20.5,8.2-20.5V80H143.1c-17.6,0-27.3-.4-28.8-1.1-3.3-1.7-5.6-5.1-5.6-8.2s5.8-39.4,7.5-47.9l.6-2.8H104.9L87.5,46.2C78,60.6,68.9,73.9,67.3,75.6S62.1,79.7,52.1,83L39.6,87.2v14.3l4.7,2.5c16.9,8.9,20.2,33.2,6.3,47-6.1,6.1-11.9,8.5-21,8.5s-14.8-2.4-21-8.5C-5.2,137.2-1.9,112.9,15,104l4.6-2.5V89.3c0-16.4.2-16.5,19.4-22.9l14.2-4.7L72.1,33.3C82.5,17.6,92.4,3.7,93.9,2.4S97.3,0,114.1,0s17.4.1,20,2.1c4.8,3.9,4.9,5.1.5,30.9-2.2,13.1-4,24.6-4,25.4s3.1,1.6,26.1,1.6h26.1l3.4,3.4,3.4,3.4V122L179,148.5c-8.4,20.9-11.2,27-13.5,29l-3,2.5H66.4Zm-28.5-38c6.7-3.5,6.5-14.3-.3-17.4-5.2-2.3-10.8-.7-13.1,3.9C16.4,134.2,25.4,143.3,34.5,138.6Z"/>
                </svg>
                Отзывы</a></li>
              <li><nuxt-link to='/FAQ'
                             onclick="document.querySelector('.mobile-nav').classList.toggle('open');
                             document.querySelector('.p_header').classList.toggle('translated');
                             document.querySelector('.p_container').classList.toggle('translated');">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 198.9 199.7">
                  <title>faq</title>
                  <path d="M93,196.1l-3.5-3.5V166.2l3.4-3.4c2.4-2.5,4.3-3.4,6.6-3.4s4.1.9,6.6,3.4,3.4,3.9,3.4,9.5,0,6.8,8,5c22.3-5,43.1-21.4,53.7-42.4a86.9,86.9,0,0,0,7.9-30.5C182.6,47.3,127,5.1,73.2,23.9A80.7,80.7,0,0,0,20.4,87.6c-1.4,8.6-.6,23.7,1.6,32.3,3.7,14.1,14.7,31.2,26.4,41,6.1,5.1,7,6.4,7,10.8a9.7,9.7,0,0,1-14.3,8.5c-4-2.1-11.9-9.3-17.5-16A105.7,105.7,0,0,1,1.8,120.9c-2.2-9.7-2.4-31.9-.4-41A102,102,0,0,1,80,1.3c7.7-1.7,31.2-1.7,39,0,39.7,8.7,69.8,38.9,78.6,78.6,1.7,7.8,1.7,31.2,0,39-9.9,44.9-46.6,76.9-91.8,80.1l-9.2.7Zm-.2-55.2-3.6-3.5.4-10.3c.3-8.7.8-11.1,3.2-15.9,3.2-6.6,7.5-10.7,15.6-14.8S119,88.2,119,79.3c0-5.4-.5-7.2-2.7-10.6-4.1-6.2-9-8.8-16.8-8.8-5.1,0-7.4.5-10.4,2.4a20.1,20.1,0,0,0-9.3,15.2c-.5,4.3-1.3,6.1-3.9,8.6-4.5,4.5-8.5,4.5-13.2-.2s-3.5-3.6-2.9-10.3c.8-8.8,6-19.4,12.2-25.2a52.4,52.4,0,0,1,11.3-7.3c6-2.9,7.6-3.2,16.2-3.2s10.1.3,16.1,3.2c9.3,4.4,15.1,10,19.6,19.1,3.6,7.2,3.8,8.1,3.8,17.1s-.3,10.2-3.2,16.2c-4.2,8.9-9.1,14.1-17,18s-9.3,6.3-9.3,16.4c0,7.4-.2,7.8-3.4,11.1s-8.6,4.6-13.3-.1Z"/>
                </svg>
                FAQ</nuxt-link></li>
            </ul>
          </div>
        </vue-scroll>
      </nav>
      <ul class="mobile-nav_socials container">
        <li><a href="#">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 261.7 213.2">
            <defs>
              <linearGradient id="gradient" x1="-110.52" y1="698.44" x2="219.83" y2="985.7"
                              gradientTransform="matrix(2.83, 0, 0, -2.83, 306.48, 2783.7)"
                              gradientUnits="userSpaceOnUse">
                <stop offset="0" stop-color="#184e68"/>
                <stop offset="1" stop-color="#57ca85"/>
              </linearGradient>
            </defs>
            <title>twitter</title>
            <path d="M74.2,213.1c-26.9-2-48.6-8.5-69.4-20.9L0,189.4l8.4.3a107.8,107.8,0,0,0,53.8-12A134.7,134.7,0,0,0,78,167.8l1.2-.9-4-.4c-15.4-1.3-30.2-10.1-39.1-23-2.7-4-6-10.3-6.6-12.8s-.3-1.3,1.9-.9c3.7.7,12.2.5,17.1-.4l4.6-.8L48,126.9A53.5,53.5,0,0,1,11.8,88.8c-1-4-2-13.5-1.3-13.5L13,76.4c4.8,2.5,14.8,5.1,19.3,5.1h1.9l-1.6-1.1c-3.2-2.3-11-10.6-13.3-14.2-8.9-14-11.1-31.7-5.6-46.9,1-3,3.5-8.5,4.1-9.1s1.1.8,2.1,2A173.8,173.8,0,0,0,37.1,29.3a151.8,151.8,0,0,0,85.3,36.3c3.3.3,6.2.5,6.3.3a13.2,13.2,0,0,0-.4-3.7c-.9-5.1-.3-16.9,1-21.8A53.1,53.1,0,0,1,144,15.5,50.2,50.2,0,0,1,161,4c19.6-7.9,41.5-4,56.6,10l3.1,2.9,3.8-.8a117.1,117.1,0,0,0,23.2-8.5c7.9-3.9,7.8-3.9,4.9,2.4a58,58,0,0,1-17.1,20.8,32.4,32.4,0,0,0-3.4,2.7c0,.2,8.2-1.3,12.3-2.3A145.4,145.4,0,0,0,261,25.8c1.2-.5,1.1-.3-2.6,4.6a128.1,128.1,0,0,1-18.2,18.8l-4.9,4,.2,3.7c.3,4.6-.6,17.7-1.7,25.1a165.5,165.5,0,0,1-19.2,55.3c-24.5,42.5-64.1,68.9-112.4,74.8-6.3.8-23,1.4-28,1Z"/>
          </svg>
        </a></li>
        <li><a href="#">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1112.6 632.5">
            <defs>
              <linearGradient id="gradient" x1="-110.52" y1="698.44" x2="219.83" y2="985.7"
                              gradientTransform="matrix(2.83, 0, 0, -2.83, 306.48, 2783.7)"
                              gradientUnits="userSpaceOnUse">
                <stop offset="0" stop-color="#184e68"/>
                <stop offset="1" stop-color="#57ca85"/>
              </linearGradient>
            </defs>

            <title>vk</title>
            <path d="M885.4,630.6c-19.2-4.5-45.7-19.2-62.9-34.9-8.6-7.9-30.4-30.9-48.4-51-57.3-64.2-75.3-72.3-99.6-44.7-14.7,16.7-20.8,37.8-24.1,83.4-1.9,26.3-3.9,31.2-16.4,40.5-5.5,4.1-10.1,4.6-55.3,5.8-75.3,2.1-109.5-2.7-158.1-22.2-43.2-17.3-103.6-57.3-140.9-93.1-48.4-46.6-121.4-148-174.1-241.6C61.8,194.9,2.7,72.4.2,54.7c-1.3-9.8,3-17.3,13.1-22.8,6.4-3.5,15.8-3.9,96.1-4.6s90-.2,98.5,3c15.4,5.9,21.1,12.3,31.2,35.3,27.8,63.6,73.2,151.3,96.6,186.5,30.4,45.7,60.9,66.9,78.6,54.5,16-11.2,25.9-68.5,24-139.3C436.1,82,425.2,57.8,384,46.5c-8.3-2.3-13.7-5-14.1-7.1s3.6-7.5,8.7-12.5C400.8,5.1,426.9,0,516.3,0c99.8,0,121.1,5.9,131.8,36.7,2.5,7,3.1,31.3,3.1,124,0,113,.1,115.5,4.6,125.3,6.5,14,15.2,21.6,24.8,21.6,6.2,0,10.7-2.4,21.8-11.6,16.5-13.6,26.7-25.5,46.1-53.7,35.3-51.4,62.1-100,87.4-158.8,17.6-40.8,21.5-47.5,29.7-51.4,3.7-1.8,38-2.8,115.1-3.3l109.9-.8,9.1,4.9c18.3,9.8,17.2,31.5-3.5,72.7-16,31.6-41.7,69.5-98.9,145.4-28.4,37.7-54.7,74.8-58.5,82.4-8.1,16.5-8.5,30.1-1.3,44.4,2.9,5.7,25.9,30.3,61.6,65.7,58.8,58.4,74.4,75.9,95.5,107.8,13.7,20.6,19.6,40.1,16.4,54.2-2,8.8-12.4,18.5-23.7,21.9-14.7,4.5-184.8,7.1-201.9,3.2Z"/>
          </svg>
        </a></li>
        <li><a href="#">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 546.1 382.9">
            <defs>
              <linearGradient id="gradient" x1="-110.52" y1="698.44" x2="219.83" y2="985.7"
                              gradientTransform="matrix(2.83, 0, 0, -2.83, 306.48, 2783.7)"
                              gradientUnits="userSpaceOnUse">
                <stop offset="0" stop-color="#184e68"/>
                <stop offset="1" stop-color="#57ca85"/>
              </linearGradient>
            </defs>

            <title>youtube-simple</title>
            <path d="M183.8,382.6c-75.5-2.1-112.9-5-128-10.1S26.9,357.3,19.7,345C5.9,321.5,0,275.5,0,191.7,0,125.1,3.9,81.1,11.8,57.3c5.5-16.7,9.3-23,19.1-32.2A66.1,66.1,0,0,1,62.8,7.9C109.1-2.7,437.4-2.6,483.7,8a67.1,67.1,0,0,1,48.1,41.5c10,25.6,12.9,52,14.1,124.2,1.5,91.9-4.5,146.5-18.7,170.5-4.4,7.3-13.9,16.9-21.7,21.9-14.6,9.4-27.1,11.6-83.4,14.6C393.9,382.1,219,383.6,183.8,382.6Zm55.3-131.8,54.4-28.3c60.7-31.3,67.5-34.9,67.9-36.2s-17.7-10.7-39.8-22.3l-60-31.2-31.3-16.4c-6.5-3.3-12.2-6.1-12.8-6.1s-1,34-1,75.6.5,75.5,1.1,75.5S227.9,256.7,239.1,250.8Z"/>
          </svg>
        </a></li>
        <li><a href="#">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 219.6 179.6">
            <defs>
              <linearGradient id="gradient" x1="-110.52" y1="698.44" x2="219.83" y2="985.7"
                              gradientTransform="matrix(2.83, 0, 0, -2.83, 306.48, 2783.7)"
                              gradientUnits="userSpaceOnUse">
                <stop offset="0" stop-color="#184e68"/>
                <stop offset="1" stop-color="#57ca85"/>
              </linearGradient>
            </defs>

            <title>mail</title>
            <path d="M3.4,176.2,0,172.8V56.4L3.4,53c2.3-2.3,4.3-3.4,6.4-3.4s13.7,6.8,41.5,24.1l38.5,24,28.6-19c32-21.3,32.4-21.4,38.2-15.7,4,4.1,4.4,8,1.2,12.1s-64.4,44.5-67.7,44.5-12.6-5.9-61.8-36.8L20,77.6v82H180V58l-3.4-1.6a29.9,29.9,0,0,1-12.7-12.2l-2.4-4.6H26.8l-3.4-3.4c-2.5-2.4-3.4-4.3-3.4-6.6s.9-4.1,3.4-6.6l3.4-3.4H161.5L164,15c8.9-16.9,33.2-20.2,47-6.4s10.6,38.1-6.4,47.1L200,58.1V172.8l-3.4,3.4-3.4,3.4H6.8Zm191.5-138c4.7-2.5,6.3-8.3,3.7-13.4-3.5-6.7-13.7-6.7-17.2,0C176.7,33.9,185.8,42.9,194.9,38.2Z"/>
          </svg>
        </a></li>
      </ul>
      <p class="copyright">(c) 2018-2019 «waxcash.net». All rights reserved.</p>
      <button class="btn btn-logout btn-dark container">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 472.6 386.1">
          <title>Exit</title>
          <path d="M71,384.8a75.3,75.3,0,0,1-24.1-8.4A88.6,88.6,0,0,1,2.1,320.5L0,312.7V73.4l2.1-7.9a90,90,0,0,1,62.6-63c7.1-2,9.1-2,63.4-2.4,62-.3,60.1-.5,63.2,5.5,1.2,2.3,1.4,5.2,1.2,14.7s-.6,12.2-2.2,14.4a10,10,0,0,1-4.2,3.2c-1.2.4-25.4.7-53.6.7-30.1.1-53.5.5-56.4,1.1-16.8,3.1-33.7,20-36.8,36.8-1.3,6.8-1.3,226.3,0,233.1,2.6,14.2,15.5,29.2,30.3,35.1,5.2,2.2,5.5,2.2,60.7,2.6,53,.5,55.5.6,58.3,2.3s4,4.4,4,17.9c.1,10.4-1.1,14.7-4.7,17.1-1.9,1.4-7.6,1.5-56.2,1.5-40-.1-55.8-.4-60.7-1.3Zm209.9-10.3a19.1,19.1,0,0,1-8.9-9.1c-1.6-3.5-1.7-7-1.7-49.2V270.7l-70-.2c-66.4-.3-70.2-.4-73.5-2s-9.7-8.4-10.6-12.6-.9-121.4,0-125.8,6-10.2,10.6-12.5,7.1-1.7,73.5-2l70-.2V70.1c0-48.8,0-49.1,4.9-54.3s16.6-7.7,23.8-3c2.2,1.4,41.8,40.4,87.8,86.6,88.4,88.6,85.8,85.7,85.8,93.6s2.6,5.1-85.8,93.7c-46,46.2-85.6,85.1-87.8,86.6s-5.1,2.7-9.7,2.6-6.8-.6-8.4-1.4Z"/>
        </svg>
        Выйти
      </button>
    </div>
  </div>
</template>

<script>
  export default {
      name: '',
      props: {
          loggedIn: {
              type: Boolean,
              required: true
          }
      },
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
              }
          }
      }
  }
</script>

<style lang="less">
  .mobile-nav {
    position: fixed;
    top: 0;
    bottom: 0;
    background: rgba(0,0,0,.55);
    z-index: 1000;
    width: 300px;
    height: 100vh;
    left: -300px;
    &_wrapper {
      border-radius: 0;
      width: 300px;
      max-height: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding-bottom: 5px;
      background: #1D1E28 linear-gradient(to right, #184e68, #57CA85) no-repeat center bottom;
      background-size: 100% 5px;
    }
    .user {
      padding: 14px 29px;
      background-color: #184E68;
      background-image: url("~/assets/images/order-total-bg.jpg");
      background-repeat: no-repeat;
      background-position: right center;
      background-size: 120% 100%;
      align-items: center;
      .avatar {
        border-radius: 10px;
        box-shadow: 0 5px 5px 0 rgba(0, 0, 0, 0.25);
        width: 50px;
        margin-right: 14px;
        overflow: hidden;
        img {
          width: 100%;
        }
      }
      .info {
        width: calc(100% - 98px);
        text-shadow: 0 6px 7px rgba(0, 0, 0, 0.25);
      }
      &_settings {
        display: flex;
        align-items: center;
        margin-top: 7px;
        .btn {
          display: inline-block;
          position: relative;
          padding: 0 10px 0 0;
          align-items: center;
          font-size: 12px;
          color: #a1c5d6;
          text-shadow: 0 6px 7px rgba(0, 0, 0, 0.25);
          &.container {
            display: flex;
            &:not(:last-of-type) {
              margin-right: 14px;
            }
            img {
              margin-right: 5px;
              display: block;
            }
            span {
              margin-left: 5px;
            }
          }
          .angle {
            transform: translate(5px, -4px) rotate(45deg);
          }
          span {
            text-shadow: 0 6px 7px rgba(0, 0, 0, 0.25);
            font-family: "SF UI Display", sans-serif;
            transform: rotate(90deg) translateY(-5px);
            margin-left: 0!important;
          }
          img {
            width: 16px;
            border-radius: 3px;
            box-shadow: 0 6px 7px 0 rgba(0, 0, 0, 0.25);
          }
          ul {
            margin: 0;
            padding: 0;
            list-style-type: none;
            position: absolute;
            top: 41px;
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
            span {
              transform: rotate(-90deg) translateY(5px);
            }
            ul {
              opacity: 1;
              transition: all 0.3s ease-out;
            }
          }
        }
      }
      .close-menu {
        width: 20px;
        font-size: 0;
        line-height: 0;
        margin-left: auto;
        svg {
          width: 20px;
          height: auto;
          path {
            fill: white;
          }
        }
      }
    }
    .balance {
      padding: 14px 29px;
      background: #17171F;
      align-items: center;
      &_wallet {
        width: 32px;
        margin-right: 14px;
        path {
          &.a {
            fill: url(#a);
          }
          &.b {
            fill: white;
          }
        }
      }
      &_info {
        p {
          font-weight: 700;
          &:first-of-type {
            color: #777d97;
            font-size: 12px;
            font-weight: 400;
          }
          span {
            color: #38df5b;
          }
        }
      }
      .btn-dark {
        width: 32px;
        padding: 7px;
        margin-left: auto;
        font-size: 0;
        line-height: 0;
        svg {
          path {
            fill: #777d97;
          }
        }
      }
    }
    .nav {
      height: calc(100% - 323px);
      margin-top: 14px;
      width: 100%;
      min-width: auto;
      &.big {
        height: calc(100% - 232px);
      }
      .scroll-wrapper {
        display: flex;
        flex-direction: column;
      }
      &-list {
        width: 100%;
        height: auto;
        list-style-type: none;
        padding-left: 0;
        li {
          padding: 0;
          margin: 0;
          a, .btn {
            font-size: 16px;
            display: flex;
            width: 100%;
            padding: 14px 29px;
            color: #777d97;
            align-items: center;
            text-decoration: none;
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
          }
        }
      }
    }
    &_socials {
      justify-content: center;
      align-items: center;
      flex-direction: row;
      flex-wrap: nowrap;
      padding: 14px;
      list-style-type: none;
      li {
        margin: 0 7px;
        a {
          display: block;
          height: 20px;
          svg {
            height: 100%;
            path {
              fill: #272938;
            }
          }
          &:hover, &:focus {
            svg {
              path {
                fill: url(#gradient);
              }
            }
          }
        }
      }
    }
    .copyright {
      font-size: 10px;
      color: #272938;
      text-align: center;
      padding: auto 29px 14px;
    }
    .btn-logout {
      margin: 29px;
      width: calc(100% - 58px);
      color: white;
      text-transform: uppercase;
      justify-content: center;
      align-items: center;
      padding: 14px;
      font-size: 16px;
      font-weight: 500;
      svg {
        height: 12px;
        margin-right: 7px;
        path {
          fill: white;
        }
      }
    }
    &.open {
      width: 100%;
      left: 0;
    }
  }
  @media screen and (min-width: 1025px) {
    .mobile-nav {
      display: none;
    }
  }
</style>

