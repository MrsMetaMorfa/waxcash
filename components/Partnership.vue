<template>
  <div class="partnership block">
      <div class="banner container">
          <div class="banner_youtube container">
              <img src="~assets/images/partnership-banner-logo-youtube.png" alt="YouTube">
          </div>
          <div class="banner_phone">
              <img src="~assets/images/partnership-banner-phone.png" alt="">
          </div>
          <div class="banner_twitch container">
              <img src="~assets/images/partnership-banner-logo-twitch.png" alt="Twitch">
          </div>
      </div>
      <div class="offer container">
          <div class="offer_famous block_light container column large">
              <div class="image_wrapper">
                  <img src="~assets/icons/youtube.svg" alt="">
              </div>
              <div class="description_wrapper">
                  <h2>Вы известная личность?</h2>
                  <p>Если у вас есть канал на ютубе или вы стримите на таких платформах  как <span class="twitch">Twitch</span> или
                      <span class="youtube">YouTube</span>, то вам предоставляется уникальная возможность сотрудничества с проектом
                      waxcash.net. Вы можете записать видео или провести стрим о нашем портале Waxcash
                      и заполнив форму ниже сообщить нам об этом.</p>
              </div>
          </div>
          <div class="offer_conditions container container--justify column small">
              <div class="condition_view block_light">
                  <div class="image_wrapper">
                      <img src="~assets/images/views.jpg" alt="">
                  </div>
                  <div class="description_wrapper">
                      <h3>Просмотры</h3>
                      <p>Минимальное количество
                          просмотров на ваших роликах</p>
                      <p class="btn-bright">20000</p>
                  </div>
              </div>
              <div class="condition_online block_light">
                  <div class="image_wrapper">
                      <img src="~assets/images/online.jpg" alt="">
                  </div>
                  <div class="description_wrapper">
                      <h3>Онлайн</h3>
                      <p>Минимальный онлайн
                          который должен быть на стриме</p>
                      <p class="btn-bright">50</p>
                  </div>
              </div>
              <div class="condition_reward block_light">
                  <div class="image_wrapper">
                      <img src="~assets/images/reward.jpg" alt="">
                  </div>
                  <div class="description_wrapper">
                      <h3>Награда</h3>
                      <p>Размер вознаграждения
                          определяется при личной беседе</p>
                      <p class="btn-bright">лично</p>
                  </div>
              </div>
          </div>
      </div>
      <form action="POST" class="partnership_form">
          <div class="container">
              <div class="column large">
                  <div class="form_line">
                      <label for="partnershipLink">Ссылка на канал:</label>
                      <div class="input_wrapper correct">
                          <input type="text" name="link" id="partnershipLink" placeholder="https://youtube.com/user/EnjoyMaloy">
                      </div>
                  </div>
                  <div class="container container--justify">
                      <div class="column">
                          <div class="form_line">
                              <label for="partnershipContent">Вы предлагаете:</label>
                              <div class="input_wrapper">
                                  <select name="content" id="partnershipContent">
                                      <option>Видео</option>
                                      <option>Стрим</option>
                                  </select>
                              </div>
                          </div>
                          <div class="form_line form_price">
                              <label for="partnershipPrice">Ваша цена (в долларах):</label>
                              <div class="input_wrapper">
                                  <input type="text" name="price" id="partnershipPrice" placeholder="50">
                              </div>
                          </div>
                      </div>
                      <div class="column">
                          <div class="form_line">
                              <label for="partnershipViews">Среднее число просмотров:</label>
                              <div class="input_wrapper">
                                  <input type="text" name="views" id="partnershipViews" placeholder="100 000">
                              </div>
                          </div>
                          <div class="form_line">
                              <label for="partnershipFollowers">Количество подписчиков:</label>
                              <div class="input_wrapper">
                                  <input type="text" name="followers" id="partnershipFollowers" placeholder="54 438">
                              </div>
                          </div>
                      </div>
                  </div>
              </div>
              <div class="column small">
                  <div class="form_line">
                      <label for="partnershipMessage">Ваше сообщение:</label>
                      <div class="input_wrapper">
                          <textarea name="message" id="partnershipMessage" placeholder="Ввести свой текст..."></textarea>
                      </div>
                  </div>
              </div>
          </div>
          <div class="container">
              <div class="column large">
                  <div class="form_line">
                      <label for="partnershipEmail">Email для связи:</label>
                      <div class="input_wrapper error">
                          <input type="email" name="email" id="partnershipEmail" placeholder="example@youremail.com">
                      </div>
                  </div>
              </div>
              <div class="column small">
                  <button class="btn btn-huge" type="submit">ОТПРАВИТЬ ЗАПРОС</button>
              </div>
          </div>
      </form>
  </div>
</template>

<script>
    export default {}
</script>

<style lang="less">
    .partnership {
        width: 100%;
        padding: 29px;
        .banner {
            position: relative;
            width: 100%;
            overflow: hidden;
            margin-bottom: 29px;
            &_phone {
              position: absolute;
              width: 332px;
              bottom: 0;
              left: 50%;
              margin-left: -166px;
            }
            &_twitch, &_youtube {
              width: 50%;
              height: 277px;
              justify-content: center;
              align-items: center;
              align-content: center;
              background-size: cover;
              background-repeat: no-repeat;
              background-position: center;
            }
            &_twitch {
              background-color: #4f17a3;
              background-image: url('~assets/images/partnership-banner-bg-right.jpg');
                padding: 0 166px;
            }
            &_youtube {
              background-color: #b6191b;
              background-image: url('~assets/images/partnership-banner-bg-left.jpg');
                padding: 0 166px;
            }
            &:before, &:after {
              position: absolute;
              display: block;
              bottom: -4px;
              z-index: 10;
              height: auto;
            }
            &:before {
              content: url("~assets/images/partnership-banner-cloud-left.png");
              left: 0;
              //943*179
            }
            &:after {
              content: url("~assets/images/partnership-banner-cloud-right.png");
              right: 0;
              //891*218
            }
        }
        .container {
            width: 100%;
        }
        .column {
            width: calc(50% - 29px);
            &.small {
                width: 41%;
                margin-left: 29px;
                min-width: 582px;
            }
            &.large {
                width: calc(59% - 29px);
            }
        }
        &_form {
            width: 100%;
            .column.small .form_line{
                height: 100%;
                .input_wrapper {
                    height: calc(100% - 48px);
                    textarea {
                        height: 100%;
                        min-height: 200px;
                    }
                }
            }
            .container:last-of-type {
                align-items: flex-end;
                .btn-huge {
                    margin-bottom: 14px;
                    width: 100%;
                    font-size: 20px;
                    line-height: 1;
                    font-weight: 700;
                }
            }
        }
    }
    .offer {
        margin-bottom: 29px;
        &_famous {
            background-image: url(~assets/images/partnership-bg.png), linear-gradient(to bottom, #2af598, #08aeea);
            background-repeat: no-repeat;
            background-size: cover, 5px 100%;
            background-position: center, left top;
            padding: 43px;
            align-items: center;
            align-content: center;
            .image_wrapper {
                width: 147px;
                margin-right: 43px;
            }
            .description_wrapper {
                width: calc(100% - 190px);
                h2 {
                    margin-bottom: 14px;
                    font-size: 20px;
                }
                p {
                    color: #737992;
                    font-size: 18px;
                    .youtube {
                        color: #ef4343;
                    }
                    .twitch {
                        color: #6d40cf;
                    }
                }
            }
        }
        &_conditions {
            .block_light {
                position: relative;
                width: calc(100% / 3 - 29px);
                display: flex;
                flex-direction: column;
                min-width: 165px;
                .image_wrapper {
                    overflow: hidden;
                    border-radius: 2px 2px 0 0;
                    img {
                        width: 100%;
                    }
                }
                .description_wrapper {
                    padding: 14px;
                    text-align: center;
                    display: flex;
                    flex-direction: column;
                    flex-grow: 3;
                    h3 {
                        margin-bottom: 7px;
                    }
                    p {
                        color: #737992;
                        margin-bottom: 14px;
                        &.btn-bright {
                            color: white;
                            margin-bottom: 0;
                            margin-top: auto;
                            &:hover, &:focus {
                                background: #5499E8;
                            }
                        }
                    }
                }
            }
            .condition {
                &_reward:before {
                    background: url("~assets/images/reward-coins.png") no-repeat center top;
                    top: -6%;
                    left: -7%;
                }
                &_online:before {
                    background: url("~assets/images/online-logos.png") no-repeat center top;
                    top: -5.5%;
                    right: -7%;
                }
                &_view:before {
                    background: url("~assets/images/views-marks.png") no-repeat center top;
                    top: 5%;
                    right: -7%;
                }
                &_reward, &_online, &_view {
                    &:before {
                        content: '';
                        display: block;
                        position: absolute;
                        width: 100%;
                        height: 100%;
                        background-size: 100% auto;
                    }
                }
            }
        }
    }
    @media screen and (max-width: 1439px) {
        .partnership {
            display: flex;
            flex-wrap: wrap;
            &_form {
                display: flex;
                flex-wrap: wrap;
                .container {
                    flex-wrap: wrap;
                }
            }
            .column {
                width: calc(50% - 14px);
            }
            .column.small {
                min-width: 0;
            }
            .offer {
                display: flex;
                flex-wrap: wrap;
                &_famous.column {
                    width: 100%;
                    margin-bottom: 29px;
                }
                &_conditions.column {
                    width: 100%;
                    margin-left: 0;
                }
            }
        }
    }
    @media screen and (max-width: 1439px) {
        .partnership {
            .banner {
                &_phone {
                    width: 240px;
                    bottom: 20px;
                    margin-left: -120px;
                }
                &_youtube {
                    padding: 0 120px 0 50px;
                }
                &_twitch {
                    padding: 0 50px 0 120px;
                }
                &:before {
                    left: -166px;
                }
                &:after {
                    right: -166px;
                }
            }
        }
    }
    @media screen and (max-width: 900px) {
        .partnership {
            &_form {
                .column {
                    &.large, &.small {
                        width: 100%;
                        margin: 0;
                    }
                }
                .container:last-of-type .btn-huge {
                    margin-bottom: 0;
                    margin-top: 15px;
                }
            }
        }
    }
    @media screen and (max-width: 767px) {
        .partnership {
            .banner {
                &_phone {
                    width: 166px;
                    bottom: 40px;
                    margin-left: -83px;
                }
                &_youtube {
                    padding: 0 83px 0 50px;
                }
                &_twitch {
                    padding: 0 50px 0 83px;
                }
            }
        }
    }
    @media screen and (max-width: 640px) {
        .partnership {
            .banner {
                &_phone {
                    display: none;
                }
                &_youtube {
                    padding: 0 30px;
                }
                &_twitch {
                    padding: 0 30px;
                }
            }
            &_form {
                .column {
                    width: 100%;
                    margin: 0;
                }
            }
        }
        .offer {
            &_famous {
                flex-wrap: wrap;
                .image_wrapper {
                    margin: 0 auto 29px;
                }
                .description_wrapper {
                    width: 100%;
                    h2 {
                        text-align: center;
                    }
                }
            }
            &_conditions {
                flex-wrap: wrap;
                .block_light {
                    width: calc(50% - 29px);
                    margin: 0 auto 29px;
                }
            }
        }
    }
    @media screen and (max-width: 480px) {
        .partnership {
            padding-left: 14px;
            padding-right: 14px;
            .banner {
                flex-wrap: wrap;
                &_youtube, &_twitch {
                    width: 100%;
                    height: 204px;
                }
                &_youtube{
                    padding-bottom: 40px;
                }
                &_twitch {
                    padding-top: 100px;
                }
                &:before {
                    bottom: 200px;
                    left: -18%;
                }
                &:after {
                    content: url("~assets/images/partnership-banner-cloud-left.png");
                    transform: scale(-1, -1);
                    top: 196px;
                    bottom: auto;
                    right: -18%;
                }
            }
        }
        .offer {
            &_famous {
                padding-left: 29px;
                padding-right: 29px;
            }
            &_conditions {
                .block_light {
                    width: 80%;
                }
            }
        }
    }
    @media screen and (max-width: 400px) {
        .partnership {
            .banner {
                &:before {
                    left: -30%;
                }
                &:after {
                    right: -30%;
                }
            }
        }
    }
</style>

