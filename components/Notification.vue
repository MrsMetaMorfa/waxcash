<template>
  <div class="notification_wrapper" id="modalNotification">
    <form class="notification block">
      <button class="btn btn-close" type="button"
              onclick="this.parentNode.parentNode.parentNode.classList.remove('active');
            this.parentNode.parentNode.classList.remove('active');"
      >
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 140 139.9">
          <title>Закрыть</title>
          <path d="M3.4,136.6C-.4,132.8-1,129,1.6,125c.9-1.4,13.4-14.3,27.8-28.8L55.5,70,29.4,43.7C15,29.3,2.5,16.4,1.6,15-1,11-.4,7.2,3.4,3.4S11-1,15,1.6c1.4.9,14.3,13.4,28.7,27.8L70,55.5,96.2,29.4C110.7,15,123.6,2.5,125,1.6c4-2.6,7.8-2,11.6,1.8S141,11,138.4,15,21.2,133.6,16.6,137.1s-8.9,3.8-13.2-.5Zm120,.5c-4.6-3.4-34.4-33.4-36.8-37.1s-2-7.8,1.8-11.6S96,84,100,86.6s33.7,32.2,37.1,36.8,3.8,8.9-.5,13.2-7.9,4.4-13.2.5Z"/>
        </svg>
      </button>
      <div class="notification_icon">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 233 52">
          <path d="M228,49.9c-9.9-4.2-17-11-19.8-21.5-3.7-13.7-11-23.7-24.7-28a10.3,10.3,0,0,0-3-.4H51C36.3,4,28.7,14.3,24.8,28.4,22,38.9,14.9,45.7,5,49.9L0,52H233Z"/>
        </svg>
        <img src="~assets/icons/notification-01.svg" alt="">
      </div>
      <h2>Ваши вещи доставлены!</h2>
      <p>Для завершения покупки примире трейд оффер</p>
      <button class="btn btn-huge" type="submit">Принять трейд</button>
      <p class="container">
        Номер заказа: <span class="number">1454574-51UZ-K1BS-WTOS</span>
      </p>
      <p class="container">
        Времени осталось:
        <data class="timer" id="timer" value="3:00">
          <span id="minutes">{{ minutes }}</span>:<span id="seconds">{{ seconds }}</span>
        </data>
      </p>
      <div class="countdown">
        <div class="bar"></div>
      </div>
      <div class="hint container">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1039 1039.6">
          <title>info-full</title>
          <path d="M480.8,1038.9c-104.4-9.7-194.6-43.9-276-104.7-25.6-19.1-80.8-74.4-100-100C61,775.5,30.5,711.3,14,642.6,2.8,596.2,0,571.3,0,519.5s2.8-76.6,14-123c16.5-68.7,47-132.9,90.8-191.6,19.2-25.6,74.4-80.9,100-100C277.6,50.6,356.9,17.7,449.7,3.6c31.5-4.8,107.1-4.8,139.9,0,90.6,13.3,171.9,47,244.5,101.3,25.7,19.1,80.9,74.4,100,100,54.4,72.7,87.2,152.1,101.3,244.9,4.8,31.5,4.8,107.1,0,139.9-8.3,56.2-24.3,108.5-48.1,157.3-27.4,56.1-54.1,93.2-100.6,139.7S803,960,746.9,987.4a526.2,526.2,0,0,1-156.2,47.8c-22.5,3.2-90.9,5.5-109.9,3.7ZM548,807.1c14.4-6.6,29-22,34.4-36.6,4.1-10.8,4.2-14.9,4.2-160.4s-.1-149.6-4.2-160.7c-4.9-12.9-19.2-28.9-31.6-35.2-18.6-9.5-44.1-9.5-62.6,0-12.4,6.3-26.8,22.3-31.6,35.2-4.2,11.1-4.2,14.5-4.2,160.7s.1,149.6,4.1,160.4c5,13.3,19.5,29.4,32.1,35.7,18.7,9.4,39.8,9.7,59.4.9Zm-.9-454.6c39.4-14.6,50.2-69.4,19.6-100.4-23.1-23.4-67.2-24.3-93.8-1.9-17.1,14.4-23.9,48.7-14,70.3,6.7,14.7,13.5,22.2,25.9,29,18.2,9.9,40.8,11,62.3,3Z"/>
        </svg>
        <p>По истечении <span>3 минут</span> трейд отклоняется и вещи возвращаются обратно к нам в магазин</p>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
      props: {
          getStartTimer: {
              type: Boolean,
              required: false
          }
      },
      data() {
          return {
              timer: null,
              totalTime: (3 * 60)
          }
      },
      methods: {
          startTimer: function() {
              this.timer = setInterval(() => this.countdown(), 1000);
          },
          padTime: function(time) {
              return (time < 10 ? '0' : '') + time;
          },
          countdown: function() {
              this.totalTime--;
          }
      },
      computed: {
          minutes: function() {
              const minutes = Math.floor(this.totalTime / 60);
              return this.padTime(minutes);
          },
          seconds: function() {
              const seconds = this.totalTime - (this.minutes * 60);
              return this.padTime(seconds);
          }
      }
  }
</script>

<style lang="less">
  .notification {
    padding: 65px 70px 70px;
    text-align: center;
    position: relative;
    background: #1D1E28;
    &_wrapper {
      padding-top: 52px;
      max-width: 618px;
      margin: auto!important;
      display: none;
      &.active {
        display: block;
      }
    }
    .btn-close {
      position: absolute;
      top: 27px;
      right: 27px;
      svg {
        width: 16px;
        path {
          fill: white;
        }
      }
    }
    &_icon {
      width: 233px;
      background: transparent url("~assets/images/modal-figure.png") no-repeat center top;
      background-size: 100% 52px;
      margin: -117px auto 0;
      padding: 23px 58px 29px;
      position: relative;
      svg {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        path {
          fill: #1D1E28;
        }
      }
      img {
        width: 55px;
        margin: 0 auto;
        position: relative;
        z-index: 1;
      }
    }
    h2 {
      font-size: 33px;
      margin-bottom: 14px;
    }
    p {
      font-size: 20px;
      margin-bottom: 29px;
      color: #777d97;
      &.container {
        margin-bottom: 14px;
        .number {
          color: #5499e8;
          margin-left: auto;
        }
        .timer {
          color: #38d75a;
          margin-left: auto;
        }
      }
    }
    .hint {
      align-items: center;
      margin-top: 20px;
      margin-bottom: 0;
      svg {
        width: 46px;
        min-width: 46px;
        margin-right: 14px;
        path {
          fill: #777d97;
        }
      }
      p {
        text-align: left;
        margin-bottom: 0;
        font-size: 16px;
      }
      span {
        color: #38d75a;
        display: inline-block;
        margin-left: 4px;
        margin-right: 4px;
      }
    }
    .btn-huge {
      width: 100%;
      font-size: 25px;
      font-weight: 700;
      margin-bottom: 14px;
    }
    .countdown {
      width: 100%;
      margin-bottom: 29px;
      background: #17171F;
      position: relative;
      height: 10px;
      border-radius: 5px;
      .bar {
        position: absolute;
        background: #17171F linear-gradient(to right, #08AEEA, #2AF598);
        height: 10px;
        border-radius: 5px;
        width: 100%;
        animation: timer 180s linear;
      }
    }
  }
  @keyframes timer {
    from {
      width: 100%;
    }
    to {
      width: 0;
    }
  }
  @media screen and (max-width: 600px) {
    .help {
      width: 100%;
      padding: 40px 20px;
      .btn-close {
        top: 14px;
        right: 14px;
      }
      h2 {
        font-size: 25px;
      }
      p {
        font-size: 16px;
      }
      .hint {
        svg {
          min-width: 30px;
        }
      }
      .btn-huge {
        font-size: 20px;
      }
    }
  }
</style>

