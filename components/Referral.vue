<template>
  <div class="referral container">
    <main class="referral_main">
        <div class="block container">
            <div class="referral_cashback">
                <h2 class="referral_title">Кэшбэк:</h2>
                <p class="block_light">5% от сделки</p>
            </div>
            <div class="referral_link">
                <h2 class="referral_title">Ваша реферальная ссылка</h2>
                <div class="container">
                    <input type="text" class="block_light" value="https://waxcash.net/referrals/1dkj439lsad">
                    <button class="btn btn-huge" type="button">СКОПИРОВАТЬ</button>
                </div>
            </div>
            <p class="referral_hint container">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1039 1039.6">
                    <title>info-full</title>
                    <path d="M480.8,1038.9c-104.4-9.7-194.6-43.9-276-104.7-25.6-19.1-80.8-74.4-100-100C61,775.5,30.5,711.3,14,642.6,2.8,596.2,0,571.3,0,519.5s2.8-76.6,14-123c16.5-68.7,47-132.9,90.8-191.6,19.2-25.6,74.4-80.9,100-100C277.6,50.6,356.9,17.7,449.7,3.6c31.5-4.8,107.1-4.8,139.9,0,90.6,13.3,171.9,47,244.5,101.3,25.7,19.1,80.9,74.4,100,100,54.4,72.7,87.2,152.1,101.3,244.9,4.8,31.5,4.8,107.1,0,139.9-8.3,56.2-24.3,108.5-48.1,157.3-27.4,56.1-54.1,93.2-100.6,139.7S803,960,746.9,987.4a526.2,526.2,0,0,1-156.2,47.8c-22.5,3.2-90.9,5.5-109.9,3.7ZM548,807.1c14.4-6.6,29-22,34.4-36.6,4.1-10.8,4.2-14.9,4.2-160.4s-.1-149.6-4.2-160.7c-4.9-12.9-19.2-28.9-31.6-35.2-18.6-9.5-44.1-9.5-62.6,0-12.4,6.3-26.8,22.3-31.6,35.2-4.2,11.1-4.2,14.5-4.2,160.7s.1,149.6,4.1,160.4c5,13.3,19.5,29.4,32.1,35.7,18.7,9.4,39.8,9.7,59.4.9Zm-.9-454.6c39.4-14.6,50.2-69.4,19.6-100.4-23.1-23.4-67.2-24.3-93.8-1.9-17.1,14.4-23.9,48.7-14,70.3,6.7,14.7,13.5,22.2,25.9,29,18.2,9.9,40.8,11,62.3,3Z"/>
                </svg>
                <span>Человек, который перешел по вашей ссылке - получает 5% кешбек с первого перевода на баланс сайта</span>
            </p>
        </div>
        <div class="block">
            <div class="tabs_wrapper referral_tabs">
                <!--sales history-->
                <input type="radio" name="history" id="historySales" aria-controls="historySalesPanel" checked>
                <label for="historySales">История продаж</label>
                <!--replenishment history-->
                <input type="radio" name="history" id="historyReplenishment" aria-controls="historyReplenishmentPanel">
                <label for="historyReplenishment">История пополнений</label>

                <div class="tab_panels">
                    <section class="tab_panel container" id="historyReferrals">
                        <div class="table">
                            <table v-show="isHistoryEmpty" class="table_empty">
                                <tbody>
                                    <tr>
                                        <td>У наших спецслужб пока еще нет данных о ваших рефералах</td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                        <Pagination v-show="!isHistoryEmpty"/>
                    </section>
                    <section class="tab_panel container" id="newReferrals">
                        <div class="table">
                            <table v-show="isNewReferralsEmpty" class="table_empty">
                                <tbody>
                                <tr>
                                    <td>У наших спецслужб пока еще нет данных о ваших рефералах</td>
                                </tr>
                                </tbody>
                            </table>
                            <table v-show="!isNewReferralsEmpty">
                                <thead>
                                    <tr>
                                        <th class="table_number">Номер</th>
                                        <th class="table_nickname">Никнэйм</th>
                                        <th class="table_time">Дата</th>
                                        <th class="table_time">Время</th>
                                        <th class="table_profit">Прибыль</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="line in historyReplenishment" :key="line.index">
                                        <td data-title="Номер" class="table_number">{{ line.id }}</td>
                                        <td data-title="Никнэйм" class="table_nickname">
                                            <p class="container">
                                                <img :src="line.avatar" :alt="line.nickname">
                                                {{ line.nickname }}
                                            </p>
                                        </td>
                                        <td data-title="Дата" class="table_time"><data :value="line.data">{{ line.data }}</data></td>
                                        <td data-title="Время" class="table_time"><data :value="line.time">{{ line.time }}</data></td>
                                        <td data-title="Прибыль" class="table_profit">{{ line.profit }}</td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                        <Pagination v-show="!isNewReferralsEmpty" />
                    </section>
                </div>
            </div>
        </div>
    </main>
    <aside class="referral_aside">
      <div class="wallet block container">
        <button class="btn wallet-menu" type="button">
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
                <g filter="url(#Filter_0)">
                    <path fill-rule="evenodd"
                          d="M6.000,10.000 L6.000,8.000 L38.000,8.000 L38.000,10.000 L6.000,10.000 ZM6.000,-0.000 L28.000,-0.000 L28.000,2.000 L6.000,2.000 L6.000,-0.000 ZM32.000,18.000 L6.000,18.000 L6.000,16.000 L32.000,16.000 L32.000,18.000 Z"/>
                </g>
            </svg>
        </button>
        <button class="btn wallet-info" type="button">
            <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 198.9 199.7">
                <defs>
                    <filter filterUnits="userSpaceOnUse" id="Filter_0" x="0px" y="0px" width="200px" height="200px"  >
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
                <title>Информация</title>
                <g>
                    <!-- filter="url(#Filter_0)" -->
                    <path fill-rule="evenodd" d="M93,196.1l-3.5-3.5V166.2l3.4-3.4c2.4-2.5,4.3-3.4,6.6-3.4s4.1.9,6.6,3.4,3.4,3.9,3.4,9.5,0,6.8,8,5c22.3-5,43.1-21.4,53.7-42.4a86.9,86.9,0,0,0,7.9-30.5C182.6,47.3,127,5.1,73.2,23.9A80.7,80.7,0,0,0,20.4,87.6c-1.4,8.6-.6,23.7,1.6,32.3,3.7,14.1,14.7,31.2,26.4,41,6.1,5.1,7,6.4,7,10.8a9.7,9.7,0,0,1-14.3,8.5c-4-2.1-11.9-9.3-17.5-16A105.7,105.7,0,0,1,1.8,120.9c-2.2-9.7-2.4-31.9-.4-41A102,102,0,0,1,80,1.3c7.7-1.7,31.2-1.7,39,0,39.7,8.7,69.8,38.9,78.6,78.6,1.7,7.8,1.7,31.2,0,39-9.9,44.9-46.6,76.9-91.8,80.1l-9.2.7Zm-.2-55.2-3.6-3.5.4-10.3c.3-8.7.8-11.1,3.2-15.9,3.2-6.6,7.5-10.7,15.6-14.8S119,88.2,119,79.3c0-5.4-.5-7.2-2.7-10.6-4.1-6.2-9-8.8-16.8-8.8-5.1,0-7.4.5-10.4,2.4a20.1,20.1,0,0,0-9.3,15.2c-.5,4.3-1.3,6.1-3.9,8.6-4.5,4.5-8.5,4.5-13.2-.2s-3.5-3.6-2.9-10.3c.8-8.8,6-19.4,12.2-25.2a52.4,52.4,0,0,1,11.3-7.3c6-2.9,7.6-3.2,16.2-3.2s10.1.3,16.1,3.2c9.3,4.4,15.1,10,19.6,19.1,3.6,7.2,3.8,8.1,3.8,17.1s-.3,10.2-3.2,16.2c-4.2,8.9-9.1,14.1-17,18s-9.3,6.3-9.3,16.4c0,7.4-.2,7.8-3.4,11.1s-8.6,4.6-13.3-.1Z"/>
                </g>
            </svg>
        </button>
        <div class="wallet_image">
          <img src="~assets/icons/new_wallet_gradient1-01.svg" alt="Wallet">
        </div>
        <div class="wallet_info">
          <h2 class="wallet_title">Ваш заработок:</h2>
          <p class="wallet_balance"><span>350.08</span> Рублей</p>
          <button class="btn btn-huge" type="button">Собрать</button>
        </div>
      </div>
      <div class="statistic block">
        <h2 class="statistic_title">Статистика</h2>
        <p class="statistic_line container container--justify">
          Приглашено пользователей <span>368</span>
        </p>
        <p class="statistic_line container container--justify">
          Всего денег заработано <span class="money">87 983 Р</span>
        </p>
        <p class="statistic_line container container--justify">
          Ваши рефералы <span>125</span>
        </p>
        <p class="statistic_line container container--justify">
          Уровень рефералки <span>2</span>
        </p>
      </div>
      <div class="system block">
        <h2 class="system_title">Реферальная система</h2>
        <button class="btn system_info" type="button" title="Подробности"><span></span><span></span><span></span></button>
        <div class="container container--justify">
          <ul class="system_steps">
            <li>1&nbsp;уровень&nbsp;(&nbsp;<span>1%</span>&nbsp;) <p>100-200</p></li>
            <li>2&nbsp;уровень&nbsp;(&nbsp;<span>2%</span>&nbsp;) <p>200-500</p></li>
            <li>3&nbsp;уровень&nbsp;(&nbsp;<span>3%</span>&nbsp;) <p>500-1000</p></li>
            <li>4&nbsp;уровень&nbsp;(&nbsp;<span>4%</span>&nbsp;) <p>1000-10000</p></li>
            <li>5&nbsp;уровень&nbsp;(&nbsp;<span>5%</span>&nbsp;) <p>10000-50000</p></li>
          </ul>
          <div class="system_level">
            <svg id="svg" width="100%" height="auto" viewBox="0 0 200 200" style="transform: rotate(-90deg)" xmlns="http://www.w3.org/2000/svg">
              <defs>
                <filter filterUnits="userSpaceOnUse" id="Filter_0" width="200%" height="200%"  >
                  <feOffset in="SourceAlpha" dx="-8" dy="0" />
                  <feGaussianBlur result="blurOut" stdDeviation="3.606" />
                  <feFlood flood-color="rgb(0, 0, 0)" result="floodOut" />
                  <feComposite operator="atop" in="floodOut" in2="blurOut" />
                  <feComponentTransfer>
                    <feFuncA type="linear" slope="0.2"/>
                  </feComponentTransfer>
                  <feMerge>
                    <feMergeNode/>
                    <feMergeNode in="SourceGraphic"/>
                  </feMerge>
                </filter>
                <linearGradient id="PSgrad_0" x1="0%" x2="100%" y1="0%" y2="50%">
                  <stop offset="0%" stop-color="rgb(8,174,234)"/>
                  <stop offset="100%" stop-color="rgb(42,245,152)"/>
                </linearGradient>
              </defs>
                <!--<g filter="url(#Filter_0)">-->
                <g>
                    <!-- Длина окружности = 2*п*r, здесь - 446 и 415, 2*71*3,14 и 2*66*3,14 соответственно -->
                    <!-- stroke-dasharray: первое число - закрашенная часть, длина окружности*%, вторая часть - прозрачная, все остальное -->
                    <!-- закрашенная часть stroke-dasharray у "фонового" кольца должно быть на 2% меньше -->
                    <!-- stroke-dashoffset: смещение по окружности - закрашенная часть-(длина окружности*1%)*-1 -->
                    <circle r="71" cx="100" cy="100"
                            fill="transparent" stroke="#1d1e28" stroke-width="20" stroke-dasharray="259, 187" stroke-dashoffset="-183"/>
                    <!-- фоновое кольцо: 58% закрашено, 42% прозрачно, смещение -59% -->
                    <!-- яркое кольцо: 40% закрашено, 60% прозрачно -->
                    <circle r="66" cx="100" cy="100"
                            fill="transparent" stroke="url(#PSgrad_0)" stroke-width="30" stroke-dasharray="166, 249"/>
                </g>
            </svg>
            <p>1 lvl</p>
          </div>
        </div>
        <div class="system_offer container">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1041.3 947.3">
            <title>Партнерство</title>
            <path d="M583.7,946.3c-24.1-3.7-39.2-11.9-62.6-34.1l-17.7-16.7-11,3.8c-12.6,4.4-37.7,5.2-51.4,1.5-32.8-8.7-58.9-37.1-65.4-71.1l-2.2-11.9-12.2-2.2c-17.1-3-32.8-11.4-46.5-24.9-12.1-11.9-22.8-31-25-44.4s-3.9-15.6-13.8-16.7c-14.8-1.7-34.7-12.3-47.8-25.4s-21.8-29-25.1-46.7l-2.2-12.3L188.5,643c-37.4-7-67.3-38.6-72.7-76.9-3.8-26.2,3.8-51.3,21.9-72.8l6.6-8-3.8-6.2c-6.8-11.2-15.8-40.3-20.4-66.3-7.8-44-2.1-35.3-63.1-96.6C10.6,269.5,2.2,260.1,1,253.8c-3.2-17-6.3-13.3,115.6-135.5C241.5-6.8,237.4-3.3,255.2,1.9c6.6,2,16.8,11,51.9,45.8,44.8,44.3,54.2,51.5,72.2,54.9,4.5.8,24.8,1.4,45.2,1.2,53-.5,87.1,6,114.4,21.7l9,5.2,25.5-3.3c14.1-1.9,37.5-4.3,52-5.5,31-2.5,48.1-5.3,58-9.4,4.3-1.8,24.5-20.2,50.8-46.4,36.2-36,45.2-43.9,52-45.7,18-4.7,14.1-8,137.8,115.4,121.1,120.9,119.5,119.1,116.5,135.9-1.3,6.8-8.7,15.1-58,64.8-31.1,31.3-57.1,58.7-57.8,60.8s-3.2,15.3-5.5,29.5c-5.4,33.6-8.9,46.6-17.6,65.7l-7.2,15.8L911,525.8c23.8,25.2,32.7,44.4,32.7,71,0,43.3-31,81.1-73.1,89.1-13.2,2.6-12.7,1.9-15.2,17.7-2.1,13-12.6,31.7-24.4,43.5-14.7,14.7-31,23-52.1,26.5-6.9,1.2-7.2,1.6-9.5,13.6-6.7,35.4-36.1,64.8-71.2,71.4l-12.4,2.3-2.2,11.3c-7.5,38-37.7,67.3-75.5,73.3-13.4,2.2-15.3,2.2-24.4.8ZM607,882.6c10.1-5.1,15.5-12.1,16.8-22.3,1.7-12.4-2.4-20.4-18.4-36.4l-15-14.9-4.7,7.8c-2.7,4.3-11.5,14.7-19.6,23.2l-14.8,15.3L565,868.9c18.9,18.7,26.7,21.3,42,13.7ZM480,838.8c2.8-1.5,16.2-13.9,29.8-27.7,20.2-20.6,25.1-26.7,27.1-34.1,6-22.3-15-42.8-37.5-36.5-6,1.6-14,8.1-32.1,25.8-28.1,27.5-32.4,33.6-32.4,45.9,0,24.3,23.2,38,45.1,26.6Zm215.9-43.1c12.5-7.4,18.3-26.9,11.8-39.5-1.3-2.6-37.4-40-80.3-83.1C545,590.2,545,590.3,548,574.5c3.5-18.6,26.6-29.5,43.5-20.5,3,1.6,38.9,36.4,79.7,77.4s77.6,76.3,81.8,78.5,10.4,3.9,13.9,3.9c14.6,0,30.4-15.8,30.4-30.4,0-3.5-1.8-9.8-3.9-13.9s-38-41.4-79.5-82.8-76.8-77.8-78.4-80.8-3-9.2-3-13.8c0-19.9,16.3-33.2,36.3-29.6,6.5,1.2,18.3,12.2,86.8,80.4,43.6,43.4,81.5,80,84.1,81.3,7.5,3.9,21.8,3,29.4-1.7,15.5-9.5,18.2-31.1,5.9-46.3-3.4-4.3-64.2-65.6-135-136.2C602.6,303,604.8,304.9,588.2,308c-6.3,1.2-15.3,9.1-57.3,50.8-27.5,27.1-54.5,52.3-60.1,55.8-36.6,23.3-84,17.6-114.5-13.6-27.2-27.9-33.1-68.1-15.4-104.1,6.6-13.3,12.7-20.4,47.4-55.7,21.9-22.3,48.1-47.9,58.1-56.9s18.6-17,19-17.8-21.7-1.9-48.8-2.4c-40.3-.7-51.7-1.6-61.3-4.6l-11.9-3.7L253,246.2l-90.4,90.5,4.3,9.8c2.4,5.4,7,24.1,10.3,41.6s7.3,36.7,9,42.6l3.2,10.9,6.5-5c9.9-7.5,25-13.5,40-15.8,47-7.3,93.3,25.6,102.1,72.5l2.2,12.2,12.3,2.3c36,6.9,67.3,38.5,72.3,73.1,1.2,9,1.9,9.8,8.4,11.4,26.2,6.3,42.9,15.5,56.5,30.9a91.5,91.5,0,0,1,21.2,43.2l2.3,12.3,9.9,1.2c5.4.6,15.6,3.7,22.6,6.7,11,4.9,19,11.8,63.5,55.7,27.9,27.6,53.1,51.7,55.8,53.6,6.7,4.4,23.2,4.3,30.9-.2Zm-306-41.3c6.6-2.5,54.4-49.1,58.7-57.3s3.7-22.2-1.7-30.3c-9.7-14.5-27.2-17.9-42.3-8.2s-51.7,48.9-54.7,58c-8.2,24.9,15.2,47,40,37.8Zm-88.8-85.3c5.2-1.5,14.7-9.6,34.9-30,29.2-29.5,32.6-35.2,29.2-48.7s-15.3-23.1-31.9-23.1H322.7l-29.5,29.3-29.5,29.3-.8,11.9c-.9,15,3.9,23.6,16.3,29.3C289.1,671.6,291.3,671.8,301.1,669.1Zm-82.8-87.7c6.3-3.3,54-50.6,57.4-57.2,1.6-3,2.9-9.2,2.9-13.8,0-20-16.3-33.2-36.2-29.5-6,1.1-12.7,6.5-34.7,28.2-33.6,33.1-37.9,41.6-29,58.3,7.4,13.9,26.4,20.6,39.6,14ZM852.8,449.9c1.7-6.4,5.1-24,7.6-39l4.3-27.3L762.8,281.7,660.9,179.8,632,182.2c-61.7,5.3-82.5,9.7-111.3,23.5-16.6,7.9-19.4,10.4-72.6,63.4-48.2,48.1-55.5,56.2-56.7,62.9-1.8,10.2,3.6,24.5,11.6,30.1s19.1,7.1,27.5,5c3.7-.9,23.8-19.3,56.6-51.7,52.4-51.8,62.3-59.6,83.1-65.3s52.3-1.8,71.7,10.4c5.5,3.4,53.9,50.1,107.6,103.6s98.2,97.5,98.9,97.5,2.7-5.3,4.4-11.7Zm79.9-150.5c18.4-17.6,33.4-32.9,33.4-34.1S796.9,93.4,794.3,93.4c-1.1,0-16.9,14.9-35.1,33.1l-33.1,33,85.9,86c47.3,47.2,86.3,85.9,86.6,85.9s15.7-14.4,34.1-32ZM271.5,97.5c-12.2-12.3-23.2-22.4-24.4-22.4S75.3,244.1,75.3,246.3s10.3,11.5,22.8,23.9L121,292.6l86.4-86.3,86.5-86.4Z"/>
          </svg>
          <p>Приглашай друзей, увеличивай свой реферальный
            уровень и получай от <span>1</span> до <span>5%</span> с их сделок</p>
        </div>
      </div>
    </aside>
  </div>
</template>

<script>
import Pagination from '~/components/pagination'

export default {
    components: {
        Pagination
    },
    name: '',
    data() {
        return {
            isHistoryEmpty: true,
            isNewReferralsEmpty: false,
            historyReplenishment: [
                {
                    id: '15',
                    nickname: 'Varner2k',
                    avatar: 'http://mrsmetamorfa.website/_nuxt/img/f850c25.jpg',
                    profit: '450.02 Р',
                    time: '19:13',
                    data: '19 января 2019'
                },
                {
                    id: '16',
                    nickname: 'Varner2k',
                    avatar: 'http://mrsmetamorfa.website/_nuxt/img/f850c25.jpg',
                    profit: '450.02 Р',
                    time: '19:13',
                    data: '19 января 2019'
                },
                {
                    id: '17',
                    nickname: 'Varner2k',
                    avatar: 'http://mrsmetamorfa.website/_nuxt/img/f850c25.jpg',
                    profit: '450.02 Р',
                    time: '19:13',
                    data: '19 января 2019'
                },
                {
                    id: '18',
                    nickname: 'Varner2k',
                    avatar: 'http://mrsmetamorfa.website/_nuxt/img/f850c25.jpg',
                    profit: '450.02 Р',
                    time: '19:13',
                    data: '19 января 2019'
                },
                {
                    id: '19',
                    nickname: 'Varner2k',
                    avatar: 'http://mrsmetamorfa.website/_nuxt/img/f850c25.jpg',
                    profit: '450.02 Р',
                    time: '19:13',
                    data: '19 января 2019'
                },
                {
                    id: '20',
                    nickname: 'Varner2k',
                    avatar: 'http://mrsmetamorfa.website/_nuxt/img/f850c25.jpg',
                    profit: '450.02 Р',
                    time: '19:13',
                    data: '19 января 2019'
                },
                {
                    id: '21',
                    nickname: 'Varner2k',
                    avatar: 'http://mrsmetamorfa.website/_nuxt/img/f850c25.jpg',
                    profit: '450.02 Р',
                    time: '19:13',
                    data: '19 января 2019'
                },
                {
                    id: '22',
                    nickname: 'Varner2k',
                    avatar: 'http://mrsmetamorfa.website/_nuxt/img/f850c25.jpg',
                    profit: '450.02 Р',
                    time: '19:13',
                    data: '19 января 2019'
                }
            ],
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
  .referral {
    width: 100%;
    &_aside {
      width: 29%;
      min-width: 472px;
      margin-left: 14px;
    }
      .wallet {
        background-image: url("~assets/images/referral-wallet-bg.jpg"), url("~assets/images/referral-wallet-bg-figures.png");
        background-size: cover, contain;
        background-position: center, left center;
        padding: 50px 29px;
        align-items: center;
        margin-bottom: 14px;
        position: relative;
        justify-content: center;
        &_image {
            width: 100px;
            height: auto;
            margin-right: 29px;
            img {
              width: 100%;
            }
        }
        &_info {
            width: auto;
        }
        &_title {
            font-size: 18px;
            font-weight: 400;
            text-shadow: 0 6px 7px rgba(0, 0, 0, 0.25);
            margin-bottom: 7px;
        }
        &_balance {
            color: white;
            font-weight: 700;
            font-size: 36px;
            text-shadow: 0 6px 7px rgba(0, 0, 0, 0.25);
            white-space: nowrap;
              margin-bottom: 14px;
            span {
              color: #39d659;
            }
        }
        .btn-huge {
            width: auto;
            text-transform: uppercase;
            font-size: 20px;
            font-weight: 700;
            padding: 10px 29px 6px;
        }
        &-menu, &-info {
            position: absolute;
            svg {
                width: 100%;
                height: auto;
                path {
                    fill: white;
                }
            }
        }
        &-menu {
            width: 45px;
            left: 14px;
            top: 20px;
        }
        &-info {
            width: 30px;
            right: 14px;
            top: 14px;
        }
    }
    .statistic {
      padding: 29px;
      margin-bottom: 14px;
      &_title {
        font-size: 20px;
        margin-bottom: 14px;
      }
      &_line {
        color: #777d97;
        margin-bottom: 14px;
        span {
          color: #5499e8;
          white-space: nowrap;
          &.money {
            color: #39d659;
          }
        }
        &:last-of-type {
          margin-bottom: 0;
        }
      }
      &_hide {
        label {
          position: relative;
          cursor: pointer;
          &:before {
            content: '';
            display: block;
            border-radius: 3px;
            background-color: rgb(84, 153, 232);
            width: 16px;
            height: 16px;
            margin-right: 14px;
            color: white;
            padding: 0 1px;
          }
        }
        input {
          border: none;
          padding: 0;
          font-size: 0;
          background: transparent;
          width: 0;
          height: 0;
          visibility: hidden;
          position: absolute;
          &:checked + label {
            &:before {
              content: url("~assets/icons/check-mark.svg");
            }
          }
        }
      }
    }
    .system {
        position: relative;
        padding: 29px;
        background-image: url(~assets/images/refsystem-bg.png);
        background-position: right top;
        background-repeat: no-repeat;
        background-size: contain;
        &_title {
        margin-bottom: 14px;
        font-size: 20px;
      }
        &_info {
            position: absolute;
            top: 29px;
            right: 29px;
            display: flex;
            padding: 9px 0;
            span {
                display: block;
                width: 6px;
                height: 6px;
                border-radius: 50%;
                background: #777d97;
                &:not(:first-of-type) {
                    margin-left: 6px;
                }
            }
        }
        > .container--justify {
            align-items: center;
        }
        &_steps {
            list-style-type: none;
            padding-left: 0;
            width: calc(100% - 170px);
            li {
                display: flex;
                align-items: center;
                color: #777d97;
                margin-bottom: 14px;
                &:before {
                    content: '';
                    display: block;
                    width: 8px;
                    height: 8px;
                    margin-right: 8px;
                    border-radius: 50%;
                    background: #ccdbef;
                }
                span {
                    color: #ccdbef;
                    display: inline-block;
                }
                p {
                    margin-left: auto;
                    color: #5499e8;
                    white-space: nowrap;
                }
                &:nth-of-type(2) {
                    &:before {
                        background: #5499e8;
                    }
                    span {
                        color: #5499e8;
                    }
                }
                &:nth-of-type(3) {
                    &:before {
                        background: #38d659;
                    }
                    span {
                        color: #38d659;
                    }
                }
                &:nth-of-type(4) {
                    &:before {
                        background: #f9c53a;
                    }
                    span {
                        color: #f9c53a;
                    }
                }
                &:nth-of-type(5) {
                    &:before {
                        background: #e92a2a;
                    }
                    span {
                        color: #e92a2a;
                    }
                }
            }
        }
        &_level {
            width: 170px;
            height: auto;
            margin-left: 14px;
            margin-right: -14px;
            position: relative;
            p {
                position: absolute;
                top: 50%;
                left: 0;
                right: 0;
                margin-top: -12px;
                text-align: center;
                font-size: 20px;
                text-transform: uppercase;
                color: #CCDBEF;
            }
        }
        &_offer {
            svg {
                margin-right: 29px;
                width: 60px;
                height: 54px;
                path {
                    fill: #5499e8;
                }
            }
            p {
                width: calc(100% - 89px);
                color: #777d97;
                span {
                    color: #39d659;
                }
            }
        }
    }

    &_main {
      width: calc(81% - 14px);
      flex-direction: column;
      min-height: calc(100% - 30px);
      height: 100%;
        .block {
            padding: 29px;
            &:not(:last-of-type) {
                margin-bottom: 14px;
            }
            &.container {
                flex-wrap: wrap;
            }
        }
    }
    &_title {
        width: 100%;
        margin-bottom: 14px;
    }
    &_cashback {
        margin-right: 29px;
        margin-bottom: 29px;
        width: 160px;
        .block_light {
            border: 1px solid;
            color: #5499e8;
            padding: 14px;
        }
    }
    &_link {
        width: calc(100% - 189px);
        margin-bottom: 29px;
        .btn-huge {
            font-size: 20px;
            font-weight: 700;
            padding: 14px 29px 11px;
            margin-left: 29px;
        }
        .block_light {
            padding: 14px;
            width: 100%;
            border: 1px solid #272938;
            color: #777d97;
        }
    }
    &_hint {
        color: #5499e8;
        align-items: center;
        svg {
            margin-right: 14px;
            width: 24px;
            height: 24px;
            path {
                fill: #5499e8;
            }
        }
    }
    &_tabs {
      width: 100%;
      height: 100%;
      display: flex;
      flex-wrap: wrap;
      .tab_panels {
        border-top: 1px solid #272938;
        padding: 14px 29px 0;
        width: calc(100% + 58px);
        margin-left: -29px;
        margin-right: -29px;
        position: relative;
        height: calc(100% - 48px);
      }
      .tab_panel {
        position: absolute;
        top: 14px;
        left: 29px;
        right: 29px;
        bottom: 0;
        display: flex;
        flex-direction: column;
        transform: scale(1, 0);
        transform-origin: top center;
        overflow: hidden;
        opacity: 0;
        height: 100%;
        .pagination {
          margin-top: auto;
          width: 100%;
          padding: 0 29px;
        }
      }
      label {
          display: inline-block;
          cursor: pointer;
          padding: 14px 0;
          color: #777d97;
          border-bottom: 4px solid transparent;
        &:not(:last-of-type) {
            margin-right: 58px;
        }
      }
      input {
        height: 0;
        width: 0;
        visibility: hidden;
        position: absolute;
        &:hover, &:checked {
          +label {
              color: #5499E8;
              border-bottom-color: #5499E8;
          }
        }
        &:first-child:checked ~ .tab_panels .tab_panel:first-child,
        &:nth-of-type(2):checked ~ .tab_panels .tab_panel:nth-of-type(2),
        &:nth-of-type(3):checked ~ .tab_panels .tab_panel:nth-of-type(3) {
          position: static;
          transform: scale(1, 1);
          opacity: 1;
          transition-delay: 0.3s;
        }
      }
    }
    .table {
      width: 100%;
      margin-bottom: 14px;
      table {
        width: 100%;
        text-align: left;
        border-collapse: collapse;
        position: relative;
      }
      thead {
        th {
          color: #272938;
          padding: 14px 29px;
          text-align: left;
          height: 48px;
          &.table_profit, &.table_time {
            color: #272938;
          }
        }
      }
      tbody {
        tr {
          &:nth-of-type(odd) {
            background: #1D1E28;
          }
          td {
            padding: 14px 29px;
          }
        }
      }
      &_time {
        color: #777d97;
          data {
              white-space: nowrap;
          }
      }
      &_nickname {
        color: #777d97;
          .container {
              align-items: center;
          }
          img {
              margin-right: 14px;
              width: 34px;
              height: 34px;
              border-radius: 2px;
          }
      }
      &_number {
        color: #5499e8;
      }
      &_profit {
        color: #38d65a;
        white-space: nowrap;
      }
        &_empty {
            tbody tr td {
                padding: 58px 29px;
                text-align: center;
                color: #777d97;
            }
        }
    }
  }
  @media screen and (max-width: 1440px) {
    .referral {
        &_aside {
        min-width: auto;
        }
        .wallet {
            &_balance {
                font-size: 28px;
            }
        }
        .system {
            .container--justify {
                flex-direction: column-reverse;
            }
            &_steps {
                width: 100%;
            }
        }
        .table {
        thead {
          th {
            padding: 14px;
          }
        }
        tbody {
          tr {
            td {
                padding-left: 14px;
                padding-right: 14px;
            }
          }
        }
      }
    }
  }
  @media screen and (max-width: 1200px) {
    .referral {
      flex-direction: column-reverse;
      &_aside {
        width: 100%;
        margin-left: 0;
        margin-bottom: 14px;
        display: flex;
        .block {
          margin-bottom: 0;
          &:not(:last-of-type) {
            margin-right: 14px;
          }
        }
        .wallet {
          width: 25%;
            min-width: 262px;
          flex-direction: column;
          align-items: center;
          justify-content: center;
          text-align: center;
          &_image {
            margin-right: auto;
            margin-left: auto;
            margin-bottom: 29px;
          }
          &_info {
            width: 100%;
          }
        }
        .statistic {
          width: calc(33% - 14px);
        }
          .system {
              width: 50%;
              .container--justify {
                  flex-direction: row;
              }
              &_steps {
                  width: calc(100% - 170px);
              }
          }
      }
      &_main {
        width: 100%;
        min-height: auto;
        height: auto;
      }
    }
  }
  @media screen and (max-width: 1000px) {
    .referral {
      &_aside {
        flex-wrap: wrap;
        margin-bottom: 0;
        .wallet {
            width: calc(50% - 7px);
          margin-right: 14px;
          margin-bottom: 14px;
            flex-direction: row;
            &_image {
                margin-right: 29px;
                margin-left: 0;
                margin-bottom: 0;
            }
            &_info {
                width: auto;
                text-align: left;
            }
        }
        .statistic {
          width: calc(50% - 7px);
          margin-right: 0!important;
          margin-bottom: 14px;
        }
        .system {
          width: 100%;
          margin-right: 0!important;
          margin-bottom: 14px;
            &_steps {
                width: 60%;
            }
            &_level {
                margin-left: auto;
                margin-right: auto;
            }
        }
      }
      &_main {
        .table {
          table {
            border: 0;
          }
          table thead {
            border: none;
            clip: rect(0 0 0 0);
            height: 1px;
            margin: -1px;
            overflow: hidden;
            padding: 0;
            position: absolute;
            width: 1px;
          }
          table tr {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
              td {
                  display: flex;
                  justify-content: space-between;
                  align-items: center;
                  width: calc(100%/2);
                  &:before {
                      content: attr(data-title);
                      margin-right: auto;
                      color: #777d97;
                  }
              }
          }
            &_empty {
                tbody tr td {
                    width: 100%;
                    display: table-cell;
                }
            }
        }
      }
        &_link {
            order: -1;
            width: 100%;
        }
        &_hint {
            width: calc(100% - 189px);
            span {
                width: calc(100% - 38px);
            }
        }
    }
  }
  @media screen and (max-width: 800px) {
      .pagination {
          flex-wrap: wrap;
          &_next, &_prev {
              width: 50%;
              order: -1;
          }
          &_prev {
              justify-content: flex-end;
          }
      }
  }
  @media screen and (max-width: 700px) {
      .referral {
          .wallet {
              flex-direction: column;
              width: auto;
              &_image {
                  margin-left: auto;
                  margin-right: auto;
                  margin-bottom: 29px;
              }
              &_info {
                  text-align: center;
              }
          }
          .statistic {
              width: calc(100% - 276px);
              p {
                  flex-wrap: wrap;
                  span {
                      margin-left: auto;
                  }
              }
          }
      }
  }
  @media screen and (max-width: 640px) {
    .referral {
      &_aside {
        .block {
          width: 100%;
          margin-right: 0!important;
          padding-left: 14px;
          padding-right: 14px;
        }
        .wallet {
          flex-direction: row;
          justify-content: center;
          &_image {
            margin-bottom: 0;
            margin-right: 29px;
            margin-left: 0;
          }
          &_info {
            text-align: left;
            width: auto;
          }
        }
      }
        &_link {
            .container {
                flex-wrap: wrap;
            }
            .btn-huge {
                margin-left: 0;
                width: 100%;
                margin-top: 14px;
            }
        }
      &_main .block{
        padding-left: 14px;
        padding-right: 14px;
      }
      .tabs_wrapper {
        .tab_panels {
          width: calc(100% + 28px);
          margin-left: -14px;
          margin-right: -14px;
          padding-left: 14px;
          padding-right: 14px;
        }
      }
    }
    .pagination {
      &_next, &_prev {
        width: 100%;
        justify-content: center;
      }
      &_next {
        order: 10;
      }
    }
  }
  @media screen and (max-width: 520px) {
      .referral {
          &_aside {
              .system {
                  .container--justify {
                      flex-direction: column-reverse;
                  }
                  &_steps {
                      width: 100%;
                  }
              }
          }
          &_hint {
              margin: 0;
              width: 100%;
          }
          &_cashback {
              width: 100%;
              margin-right: 0;
              display: flex;
              margin-bottom: 29px;
              align-items: center;
              .referral_title {
                  width: calc(50% - 14px);
                  margin-right: 14px;
                  margin-bottom: 0;
              }
              .block_light {
                  width: 50%;
              }
          }
          &_main {
              .table {
                  table tr td {
                      width: 100%;
                  }
              }
          }
          .tabs_wrapper {
              label {
                  width: calc((100% - 28px)/2);
                  text-align: center;
                  &:not(:last-of-type) {
                      margin-right: 14px;
                  }
              }
          }
      }
  }
</style>

