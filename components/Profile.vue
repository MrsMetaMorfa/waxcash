<template>
  <div class="profile container">
    <aside class="profile_aside">
      <div class="user block container">
        <div class="user_avatar">
          <img src="~assets/images/avatar.jpg" alt="Verner2k">
        </div>
        <div class="user_info">
          <h2 class="user_nickname">Verner2k</h2>
          <p class="user_balance">Баланс: <span>45 000 Р</span></p>
        </div>
      </div>
      <div class="statistic block">
        <h2 class="statistic_title">Статистика</h2>
        <p class="statistic_line container container--justify">
          Трейдов сделано <span>68</span>
        </p>
        <p class="statistic_line container container--justify">
          Всего оборота <span class="money">87 983 Р</span>
        </p>
        <p class="statistic_line container container--justify">
          Потрачено в магазине <span class="money">5 609 Р</span>
        </p>
        <p class="statistic_line container container--justify">
          Ваша скидка <span>3%</span>
        </p>
        <div class="statistic_hide">
          <input type="checkbox" id="hideMyStatictic" checked>
          <label for="hideMyStatictic" class="container">Скрывать мои выводы в ленте</label>
        </div>
      </div>
      <div class="trade-url block">
        <h2 class="trade-url_title">Ваш OPskins Trade URL:</h2>
        <div class="input_wrapper correct">
          <input type="text" name="OPskinsTradeLink" id="OPskinsTradeLink" placeholder="Введите ссылку на обмен...">
        </div>
        <button class="btn btn-huge" type="submit">Подтвердить</button>
        <p class="find-link">
          <a href="#">Нажмите чтобы найти Trade URL</a>
        </p>
      </div>
    </aside>
    <main class="profile_main block container">
      <h2 class="profile_title">Информация</h2>
      <div class="tabs_wrapper">
          <!--sales history-->
          <input type="radio" name="history" id="historySales" aria-controls="historySalesPanel" checked>
          <label class="btn btn-dark" for="historySales">История продаж</label>
          <!--replenishment history-->
          <input type="radio" name="history" id="historyReplenishment" aria-controls="historyReplenishmentPanel">
          <label class="btn btn-dark" for="historyReplenishment">История пополнений</label>
          <!--purchase history-->
          <input type="radio" name="history" id="historyPurchase" aria-controls="historyPurchasePanel">
          <label class="btn btn-dark" for="historyPurchase">История покупок</label>

        <div class="tab_panels">
          <section class="tab_panel container" id="historySalesPanel">
            <div class="table">
              <table>
                <thead>
                  <tr>
                    <th>ID</th>
                    <th>Кошелек</th>
                    <th class="table_summary">Сумма</th>
                    <th class="table_trade">Трэйд</th>
                    <th class="table_status">Статус</th>
                    <th class="table_time">Время</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="line in historySales" :key="line.index">
                    <td data-title="ID" class="table_id">{{ line.id }}</td>
                    <td data-title="Кошелек" class="table_wallet">{{ line.wallet }}</td>
                    <td data-title="Сумма" class="table_summary">{{ line.summary }}</td>
                    <td data-title="Трэйд" class="table_trade"><a class="btn btn-dark" :href="line.trade">Открыть</a></td>
                    <td data-title="Статус" class="table_status"><p :class="line.status">{{ line.statusMessage }}</p></td>
                    <td data-title="Время" class="table_time"><data :value="line.time">{{ line.time }}</data></td>
                  </tr>
                </tbody>
              </table>
            </div>
            <Pagination />
          </section>
          <section class="tab_panel container" id="historyReplenishmentPanel">
            <div class="table">
              <table>
                <thead>
                <tr>
                  <th>ID</th>
                  <th class="table_summary">Сумма</th>
                  <th class="table_status">Статус</th>
                  <th class="table_time">Время</th>
                </tr>
                </thead>
                <tbody>
                <tr v-for="line in historyReplenishment" :key="line.index">
                  <td data-title="ID" class="table_id">{{ line.id }}</td>
                  <td data-title="Сумма" class="table_summary">{{ line.summary }}</td>
                  <td data-title="Статус" class="table_status"><p :class="line.status">{{ line.statusMessage }}</p></td>
                  <td data-title="Время" class="table_time"><data :value="line.time">{{ line.time }}</data></td>
                </tr>
                </tbody>
              </table>
            </div>
            <Pagination />
          </section>
          <section class="tab_panel container" id="historyPurchasePanel">
            <div class="table table_opened">
              <table>
                <thead>
                <tr>
                  <th>ID</th>
                  <th class="table_skins">Скины</th>
                  <th class="table_summary">Сумма</th>
                  <th class="table_trade">Трэйд</th>
                  <th class="table_status">Статус</th>
                  <th class="table_time">Время</th>
                </tr>
                </thead>
                <tbody v-for="line in historyPurchase" :key="line.index">
                  <tr>
                    <td data-title="ID" class="table_id">{{ line.id }}</td>
                    <td data-title="Скины" class="table_skins">
                      <button class="btn open-list"
                              onclick="this.parentNode.parentNode.parentNode.classList.toggle('open')">
                        <span class="open-list">Посмотреть</span>
                        <span class="close-list">Скрыть</span>
                      </button>
                    </td>
                    <td data-title="Сумма" class="table_summary">{{ line.summary }}</td>
                    <td data-title="Трэйд" class="table_trade"><a class="btn btn-dark" :href="line.trade">Открыть</a></td>
                    <td data-title="Статус" class="table_status"><p :class="line.status">{{ line.statusMessage }}</p></td>
                    <td data-title="Время" class="table_time"><data :value="line.time">{{ line.time }}</data></td>
                  </tr>
                  <tr>
                    <td colspan="6" class="table_list">
                      <div class="container">
                        <vue-scroll :ops="opsVertical">
                          <ul class="container">
                            <li class="block_light" :key="item.index" v-for="item in line.list">
                              <img :src="item.image" :alt="item.title" :title="item.title">
                            </li>
                          </ul>
                        </vue-scroll>
                      </div>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
            <Pagination />
          </section>
        </div>
      </div>
    </main>
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
            historySales: [
                {
                    id: '458632',
                    wallet: 'XXXX XXXX XXXX 9813',
                    summary: '450.02 Р',
                    trade: '#tradelink',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    wallet: '+380994389950',
                    summary: '8 655.00 Р',
                    trade: '#tradelink',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                },
                {
                    id: '348854',
                    wallet: 'R43258123647435',
                    summary: '13 450.13 Р',
                    trade: '#tradelink',
                    status: 'cancel',
                    statusMessage: 'Отменено',
                    time: '15:51 31 января 2019'
                },
                {
                    id: '458632',
                    wallet: 'XXXX XXXX XXXX 9813',
                    summary: '450.02 Р',
                    trade: '#tradelink',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    wallet: '+380994389950',
                    summary: '8 655.00 Р',
                    trade: '#tradelink',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                },
                {
                    id: '348854',
                    wallet: 'R43258123647435',
                    summary: '13 450.13 Р',
                    trade: '#tradelink',
                    status: 'cancel',
                    statusMessage: 'Отменено',
                    time: '15:51 31 января 2019'
                },
                {
                    id: '458632',
                    wallet: 'XXXX XXXX XXXX 9813',
                    summary: '450.02 Р',
                    trade: '#tradelink',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    wallet: '+380994389950',
                    summary: '8 655.00 Р',
                    trade: '#tradelink',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                },
                {
                    id: '348854',
                    wallet: 'R43258123647435',
                    summary: '13 450.13 Р',
                    trade: '#tradelink',
                    status: 'cancel',
                    statusMessage: 'Отменено',
                    time: '15:51 31 января 2019'
                },
                {
                    id: '458632',
                    wallet: 'XXXX XXXX XXXX 9813',
                    summary: '450.02 Р',
                    trade: '#tradelink',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    wallet: '+380994389950',
                    summary: '8 655.00 Р',
                    trade: '#tradelink',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                }
            ],
            historyReplenishment: [
                {
                    id: '458632',
                    summary: '450.02 Р',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    summary: '8 655.00 Р',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                },
                {
                    id: '348854',
                    summary: '13 450.13 Р',
                    status: 'cancel',
                    statusMessage: 'Отменено',
                    time: '15:51 31 января 2019'
                },
                {
                    id: '458632',
                    summary: '450.02 Р',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    summary: '8 655.00 Р',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                },
                {
                    id: '348854',
                    summary: '13 450.13 Р',
                    status: 'cancel',
                    statusMessage: 'Отменено',
                    time: '15:51 31 января 2019'
                },
                {
                    id: '458632',
                    summary: '450.02 Р',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    summary: '8 655.00 Р',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                },
                {
                    id: '348854',
                    summary: '13 450.13 Р',
                    status: 'cancel',
                    statusMessage: 'Отменено',
                    time: '15:51 31 января 2019'
                },
                {
                    id: '458632',
                    summary: '450.02 Р',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    summary: '8 655.00 Р',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                }
            ],
            historyPurchase: [
                {
                    id: '458632',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '450.02 Р',
                    trade: '#tradelink',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '8 655.00 Р',
                    trade: '#tradelink',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                },
                {
                    id: '348854',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '13 450.13 Р',
                    trade: '#tradelink',
                    status: 'cancel',
                    statusMessage: 'Отменено',
                    time: '15:51 31 января 2019'
                },
                {
                    id: '458632',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '450.02 Р',
                    trade: '#tradelink',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '8 655.00 Р',
                    trade: '#tradelink',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                },
                {
                    id: '348854',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '13 450.13 Р',
                    trade: '#tradelink',
                    status: 'cancel',
                    statusMessage: 'Отменено',
                    time: '15:51 31 января 2019'
                },
                {
                    id: '458632',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '450.02 Р',
                    trade: '#tradelink',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '8 655.00 Р',
                    trade: '#tradelink',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
                },
                {
                    id: '348854',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '13 450.13 Р',
                    trade: '#tradelink',
                    status: 'cancel',
                    statusMessage: 'Отменено',
                    time: '15:51 31 января 2019'
                },
                {
                    id: '458632',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '450.02 Р',
                    trade: '#tradelink',
                    status: 'waiting',
                    statusMessage: 'В обработке',
                    time: '19:13 19 января 2019'
                },
                {
                    id: '658125',
                    list: [
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        },
                        {
                            image: 'http://mrsmetamorfa.website/_nuxt/img/52cb446.png',
                            title: ''
                        }
                    ],
                    summary: '8 655.00 Р',
                    trade: '#tradelink',
                    status: 'success',
                    statusMessage: 'Отправлено',
                    time: '03:26 8 января 2019'
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
  .profile {
    width: 100%;
    &_aside {
      width: 19%;
      min-width: 360px;
      margin-right: 14px;
    }
    .user {
      background-image: url("~assets/images/user-bg.jpg");
      background-size: cover;
      background-position: center;
      padding: 29px;
      align-items: center;
      margin-bottom: 14px;
      &_avatar {
        width: 70px;
        height: 70px;
        margin-right: 29px;
        img {
          object-fit: cover;
          height: 100%;
        }
      }
      &_info {
        width: calc(100% - 99px);
      }
      &_nickname {
        font-size: 20px;
        font-weight: 700;
        margin-bottom: 14px;
      }
      &_balance {
        color: #777d97;
        span {
          color: #39d659;
          text-transform: uppercase;
          white-space: nowrap;
        }
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
          margin-bottom: 29px;
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
    .trade-url {
      padding: 29px;
      &_title {
        margin-bottom: 14px;
        font-size: 20px;
      }
      .btn-huge {
        width: 100%;
        margin-bottom: 14px;
        font-size: 20px;
        font-weight: 700;
        padding: 12px 14px 10px;
      }
      .find-link {
        text-align: center;
        a {
          display: inline-block;
          text-align: center;
          color: #5499e8;
          text-decoration: none;
          border-bottom: 1px solid transparent;
          &:hover, &:focus {
            border-bottom-color: #5499e8;
          }
        }
      }
    }

    &_main {
      width: calc(81% - 14px);
      padding: 29px;
      flex-direction: column;
      min-height: calc(100% - 30px);
      height: 100%;
    }
    &_title {
      width: 100%;
      margin-bottom: 14px;
    }
    .tabs_wrapper {
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
        margin-bottom: 14px;
        display: flex;
        align-items: center;
        &:not(:last-of-type) {
          margin-right: 14px;
        }
      }
      input {
        height: 0;
        width: 0;
        visibility: hidden;
        position: absolute;
        &:hover, &:checked {
          +label {
            background: #5499E8;
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
          &.table_summary, &.table_time {
            color: #272938;
          }
          &.table_status, &.table_trade, &.table_skins {
            text-align: center;
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
      &_wallet, &_time {
        color: #777d97;
      }
      &_trade, &_status {
        text-align: center;
      }
      &_trade {
        .btn-dark {
          text-decoration: none;
          color: #777d97;
          &:hover, &:focus {
            color: white;
          }
        }
      }
      &_status {
        p {
          max-width: 150px;
          margin: 0 auto;
          border-radius: 2px;
          padding: 8px 14px 6px;
          width: 100%;
          white-space: nowrap;
          &.waiting {
            background: #3D6EA5;
          }
          &.success {
            background: #3EA655;
          }
          &.cancel {
            background: #A83B3B;
          }

        }
      }
      &_id {
        color: #5499e8;
      }
      &_summary {
        color: #38d65a;
        width: 160px;
        white-space: nowrap;
      }
      &_time {
        width: 240px;
      }
      &_opened {
        .table_skins {
          width: 210px;
          .btn {
            text-decoration: underline;
            text-align: center;
            display: flex;
            flex-direction: column;
            color: #5499e8;
            position: relative;
            height: 16px;
            width: 100%;
            font-size: 16px;
            span {
              position: absolute;
              top: 0;
              left: 0;
              right: 0;
              text-align: center;
              text-decoration: underline;
            }
            .open-list {
              opacity: 1;
            }
            .close-list {
              opacity: 0;
            }
            &:hover, &:focus {
              color: white;
            }

          }
        }
        tbody {
          tr:nth-of-type(odd) {
            background: transparent;
          }
          &:nth-of-type(odd) {
            background: #1D1E28;
          }
          .table_list {
            transform: scale(1, 0);
            transform-origin: top center;
            padding: 0;
            height: 0;
            position: relative;
            overflow: hidden;
            > .container {
              position: absolute;
              top: 0;
              left: 0;
              right: 0;
              bottom: 0;
            }
            ul {
              border-top: 1px solid #272938;
              list-style-type: none;
              padding: 29px;
              margin: 0;
              li {
                height: 66px;
                width: 66px;
                display: flex;
                justify-content: center;
                align-items: center;
                padding: 7px;
                img {
                  max-width: 100%;
                  max-height: 100%;
                  filter: drop-shadow(0 2px 2px black);
                }
                &:not(:last-of-type) {
                  margin-right: 29px;
                }
              }
            }
          }
          &.open {
            .table_skins {
              .btn {
                color: white;
                .open-list {
                  opacity: 0;
                }
                .close-list {
                  opacity: 1;
                }
                &:hover, &:focus {
                  color: #5499e8;
                }
              }
            }
            .table_list {
              opacity: 1;
              transform: scale(1, 1);
              height: 125px;
            }
          }
        }
      }
    }
  }
  @media screen and (max-width: 1440px) {
    .profile {
      &_aside {
        width: 310px;
        min-width: auto;
      }
      &_main {
        width: calc(100% - 324px);
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
              padding: 14px;
            }
          }
        }
        &_time {
          width: 190px;
        }
        &_summary {
          width: 130px;
        }
        &_opened {
          .table_skins {
            width: 150px;
          }
        }
      }
    }
  }
  @media screen and (max-width: 1260px) {
    .profile {
      flex-direction: column;
      &_aside {
        width: 100%;
        margin-right: 0;
        margin-bottom: 14px;
        display: flex;
        .block {
          margin-bottom: 0;
          &:not(:last-of-type) {
            margin-right: 14px;
          }
        }
        .user {
          width: 25%;
          flex-direction: column;
          align-items: center;
          justify-content: center;
          text-align: center;
          padding: 14px;
          &_avatar {
            margin-right: auto;
            margin-left: auto;
            margin-bottom: 29px;
          }
          &_info {
            width: 100%;
          }
        }
        .statistic, .trade-url {
          width: calc(75%/2 - 14px);
        }
      }
      &_main {
        width: 100%;
        min-height: auto;
        height: auto;
      }
    }
  }
  @media screen and (max-width: 860px) {
    .profile {
      &_aside {
        flex-wrap: wrap;
        margin-bottom: 0;
        .user {
          width: 40%;
          margin-right: 14px;
          margin-bottom: 14px;
        }
        .statistic {
          width: 100%;
          margin-right: 0!important;
          margin-bottom: 14px;
          order: 1;
          display: flex;
          flex-wrap: wrap;
          justify-content: space-between;
          &_title {
            width: 100%;
          }
          &_line {
            width: calc((100% - 29px)/2);
          }
          &_hide {
            width: 100%;
          }
        }
        .trade-url {
          width: calc(60% - 14px);
          margin-right: 0!important;
          margin-bottom: 14px;
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
          }
          table td {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: calc(100%/2);
          }
          table td::before {
            content: attr(data-title);
            margin-right: auto;
            color: #777d97;
          }
          &_time, &_summary, &_trade, &_id, &_wallet {
            text-align: right;
          }
          &_status {
            p {
              margin-right: 0;
            }
          }
          &_opened {
            .table_skins {
              width: calc(100%/2);
              order: 1;
              .btn {
                width: 90px;
                span {
                  text-align: right;
                }
              }
            }
            .table_list {
              width: 100%;
            }
            tbody{
              tr:last-of-type {
                height: 0;
              }
              &.open {
                tr:last-of-type {
                  height: 125px;
                }
              }
            }
          }
        }
      }
    }
  }
  @media screen and (max-width: 800px) {
    .profile .tabs_wrapper label {
      padding-left: 14px;
      padding-right: 14px;
    }
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
  @media screen and (max-width: 640px) {
    .profile {
      &_aside {
        .statistic_line {
          width: 100%;
        }
      }
      .tabs_wrapper {
        label {
          width: calc((100% - 28px)/3);
          text-align: center;
        }
      }
      &_main {
        .table {
          table tbody tr td {
            width: 100%;
          }
          &_opened {
            .table_skins {
              width: 100%;
            }
          }
        }
      }
    }
  }
  @media screen and (max-width: 500px) {
    .profile {
      &_aside {
        .block {
          width: 100%;
          margin-right: 0!important;
          padding-left: 14px;
          padding-right: 14px;
        }
        .user {
          flex-direction: row;
          justify-content: center;
          &_avatar {
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
      &_main {
        padding-left: 14px;
        padding-right: 14px;
      }
      .tabs_wrapper {
        label {
          width: 100%;
          margin-right: 0!important;
        }
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
</style>

