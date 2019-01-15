<template>
  <form class="block p_main-right container container--justify">
    <div class="block_total">
      <p>Вы получите: <span class="total">11500.47 Р</span></p>
      <p class="small">Теперь выберите платежную систему и введите данные для получения средств на кошелек</p>
      <input type="disabled" disabled hidden value="11500.47" name="total">
    </div>
    <div class="block_payment container container--justify">
      <div class="system">
        <input type="radio" name="system" id="system1" value="qiwi">
        <label for="system1"><img src="~assets/images/Qiwi.png" alt="QIWI"></label>
      </div>
      <div class="system">
        <input type="radio" name="system" id="system2" value="Yandex.Money">
        <label for="system2"><img src="~assets/images/YaM.png" alt="Yandex.Money"></label>
      </div>
      <div class="system">
        <input type="radio" name="system" id="system3" value="Visa">
        <label for="system3"><img src="~assets/images/Visa.png" alt="Visa"></label>
      </div>
      <div class="system">
        <input type="radio" name="system" id="system4" value="MasterCard">
        <label for="system4"><img src="~assets/images/MasterCard.png" alt="MasterCard"></label>
      </div>
      <div class="system">
        <input type="radio" name="system" id="system5" value="World">
        <label for="system5"><img src="~assets/images/World.png" alt="World"></label>
      </div>
      <div class="system">
        <input type="radio" name="system" id="system6" value="Maestro">
        <label for="system6"><img src="~assets/images/Maestro.png" alt="Maestro"></label>
      </div>
    </div>
    <div class="block_info">
      <div class="line">
        <label for="email">Ваш email:</label>
        <div class="input_wrapper">
          <input type="email" name="email" id="email" placeholder="verner2k@example.com"></div>
      </div>
      <div class="line">
        <label for="purse">Ваш Кошелек:</label>
        <div class="input_wrapper current">
          <input type="text" name="purse" id="purse" value="XXXX XXXX XXXX XXXX"></div>
      </div>
      <div class="line">
        <label for="user">ФИО:</label>
        <div class="input_wrapper">
          <input type="text" name="user" id="user" placeholder="Вернер Давид Матвеевич"></div>
      </div>
      <div class="line">
        <p class="hint">Для карта Visa и MasterCard взымается комиссия 40 рублей + 2%</p>
        <p class="warning">Перевод осуществляется только на карты российских банков!</p>
      </div>
    </div>
    <div class="btn-submit">
      <button type="submit" class="btn">Продать</button>
    </div>
  </form>
</template>

<style lang="less">
  .p_main-right {
    width: 36.54568% !important;
    min-width: 500px !important;
    margin-left: 14px;
    flex-direction: column;
  }
  .block_total {
    border-radius: 9px;
    background: rgb(39, 41, 56) url("~assets/images/total-bg.jpg") no-repeat right bottom;
    background-size: auto 100%;
    width: 100%;
    height: 143px;
    position: relative;
    padding: 20px 114px 14px 14px;
    p {
      font-size: 28px;
      line-height: 34px;
      margin-bottom: 14px;
      font-weight: 700;
      display: flex;
      flex-wrap: wrap;
      .total {
        font-size: 34px;
        color: rgb(56, 215, 90);
        font-weight: 700;
        text-shadow: 0px 7px 8px rgba(0, 0, 0, 0.3);
        display: inline-block;
        margin-left: auto;
        white-space: nowrap;
      }
      &.small {
        font-size: 16px;
        font-weight: 400;
        line-height: 1.4;
        padding-right: 30px;
        color: #b6d0ea;
      }
    }
    &:after {
      content: url("~assets/images/total-character.png");
      display: block;
      position: absolute;
      bottom: -6px;
      right: -14px;
    }
  }
  .block_payment {
    width: calc(100% + 14px);
    margin: 0 -7px;
    flex-wrap: wrap;
    .system {
      padding: 0 7px 14px;
      width: calc(100%/3);
      input {
        width: 0;
        height: 0;
        visibility: hidden;
        position: absolute;
        opacity: 0;
      }
      label {
        width: 100%;
        border-radius: 1px;
        background-color: rgb(39, 41, 56);
        height: 62px;
        padding: 14px;
        display: flex;
        align-items: center;
        cursor: pointer;
        img {
          margin: auto;
          max-height: 100%;
        }
      }
      input:checked + label, label:hover {
        background-image: linear-gradient(to right, rgba(8, 174, 234, 0.4), rgba(42, 245, 152, 0.4));
      }
    }
  }
  .block_info {
    padding: 0;
  .line {
    label {
      display: block;
      margin-bottom: 14px;
    }
    .input_wrapper {
      position: relative;
      margin-bottom: 14px;
      &.current {
        input {
          padding-right: 30px;
        }
        &:after {
          content: url("~assets/images/check.png");
          display: block;
          border-radius: 50%;
          background-color: rgba(56, 223, 90, 0.149);
          position: absolute;
          width: 20px;
          height: 20px;
          color: rgb(56, 223, 90);
          top: 12px;
          right: 16px;
          z-index: 1;
          text-align: center;
        }
      }
    }
    input {
      display: block;
      width: 100%;
      border-radius: 2px;
      background-color: rgb(39, 41, 56);
      padding: 12px 14px;
      line-height: 1.75;
      color: white;
      position: relative;
      z-index: 1;
      border: 2px solid transparent;
      &:hover, &:focus {
        border-image: linear-gradient(to right, rgba(8, 174, 234, 1) 0%, rgba(42, 245, 152, 1) 100%);
        border-image-slice: 1;
      }
    }
    .hint {
      text-align: center;
      margin-top: 29px;
      line-height: 1.4;
    }
    .warning {
      text-align: center;
      color: #e22e2e;
      line-height: 1.4;
    }
  }
  }
  .btn-submit {
    .btn {
      width: 100%;
      display: block;
      padding: 14px;
      text-transform: uppercase;
      border-radius: 2px;
      background-color: rgb(56, 223, 90);
      font-size: 25px;
      font-weight: 700;
    }
  }
  @media screen and (max-width: 1825px) {
    .block_total p {
      font-size: 23px;
      .total {
        font-size: 29px;
      }
    }
  }
  @media screen and (max-width: 1825px) {
    .p_main-right {
      min-width: 400px;
      .block_total {
        height: auto;
        p {
          .total {
            margin-right: auto;
          }
        }
      }
    }
  }
  @media screen and (max-width: 1072px) {
    .p_main-right {
      width: 100%;
      margin-left: 0;
      margin-top: 14px;
      flex-wrap: wrap;
      height: 510px;
      .block_total, .block_payment {
        width: 50%;
        margin: auto 29px auto 0;
      }
      .block_info, .btn-submit {
        width: calc(50% - 29px);
        .hint {
          margin-top: 0;
        }
      }
    }
  }
  @media screen and (max-width: 800px) {
    .p_main-right {
      height: 600px;
      .block_total, .block_payment {
        width: calc(50% - 29px);
        .system {
          width: 50%;
        }
      }
      .block_info, .btn-submit {
        width: 50%;
        margin: auto 0;
      }
    }
  }
  @media screen and (max-width: 767px) {
    .p_main-right {
      flex-direction: row;
      height: auto;
      .block_payment {
        width: 100%;
        margin-right: 0;
        margin-top: 14px;
        .system {
          width: calc(100%/3);
        }
      }
      .block_total {
        width: 100%;
        margin-right: 0;
        background-size: 100% 100%;
      }
      .block_info, .btn-submit {
        width: 100%;
        margin-top: 14px;
      }
    }
  }
  @media screen and (max-width: 480px) {
    .p_main-right {
      min-width: auto;
      .block_payment {
        .system {
          width: calc(100%/2);
        }
      }
    }
  }
  @media screen and (max-width: 420px) {
    .p_main-right {
      min-width: auto;
      .block_total {
        p {
          .total {
            margin-right: 0;
          }
          &.small {
            padding-right: 124px;
          }
        }
      }
    }
  }
  @media screen and (max-width: 380px) {
    .p_main-right {
      .block_total {
        padding-bottom: 160px;
        padding-right: 14px;
        p {
          &.small {
            padding-right: 0;
          }
        }
      }
      .block_payment {
        .system {
          width: 100%;
        }
      }
    }
  }
</style>

