<template>
  <form class="block p_main-right container">
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
      <div class="line form_line">
        <label for="email">Ваш email:</label>
        <div class="input_wrapper">
          <input type="email" name="email" id="email" placeholder="verner2k@example.com"></div>
      </div>
      <div class="line form_line">
        <label for="purse">Ваш Кошелек:</label>
        <div class="input_wrapper correct">
          <input type="text" name="purse" id="purse" value="XXXX XXXX XXXX XXXX"></div>
      </div>
      <div class="line form_line">
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
      <button type="submit" class="btn btn-huge">Продать</button>
    </div>
  </form>
</template>

<style lang="less">
  .p_main-right {
    width: 36.54568%;
    min-width: 500px;
    margin-left: 14px;
    flex-direction: column;
    padding: 29px;
  }
  .block_total {
    border-radius: 9px;
    background: rgb(39, 41, 56) url("~assets/images/total-bg.jpg") no-repeat right bottom;
    background-size: 100% 100%;
    width: 100%;
    height: 143px;
    position: relative;
    padding: 20px 160px 14px 14px;
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
    margin: 29px -7px 0;
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
    margin-top: 29px;
  }
  .line {
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
  .btn-submit {
    margin-top: 29px;
    .btn {
      width: 100%;
      display: block;
      font-size: 25px;
      font-weight: 700;
    }
  }

  @media screen and (max-width: 2048px) {
    .p_main-right {
      justify-content: space-between;
    }
    .block_total {
      padding-right: 114px;
    }
  }
  @media screen and (max-width: 1824px) {
    .block_total {
      height: auto;
      p {
        font-size: 23px;
        .total {
          margin-right: auto;
          font-size: 29px;
        }
      }
    }
  }
  @media screen and (max-width: 1640px) {
    .p_main-right {
      min-width: auto;
      width: 580px;
    }
  }
  @media screen and (max-width: 1360px) {
    .p_main-right {
      width: 43.54354%;
      min-width: 400px;
    }
    .block_total {
      padding-top: 7px;
      min-height: 140px;
      p {
        margin-bottom: 7px;
      }
    }
  }
  @media screen and (max-width: 1250px) {
    .block_total {
      //padding-right: 14px;
      //padding-top: 14px;
      //&:after {
        //display: none;
      //}
    }
  }
  @media screen and (max-width: 1146px) {
    .p_main-right {
      width: 100%;
      min-width: 0;
      margin-left: 0;
      margin-top: 14px;
      flex-wrap: wrap;
      height: 570px;
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
  @media screen and (max-width: 980px) {
    .p_main-right .block_total {
      padding-right: 14px;
    }
    .block_total:after {
      display: none;
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
      }
      .block_info, .btn-submit {
        width: 100%;
        margin-top: 14px;
      }
    }
    .p_main-right .block_total {
      padding-right: 114px;
    }
    .block_total:after {
      display: block;
    }

  }
  @media screen and (max-width: 540px) {
    .p_main-right .block_total {
      padding-right: 14px;
    }
    .block_total:after {
      display: none;
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
        padding: 14px;
        &:after {
          display: none;
        }
      }
    }
  }
  @media screen and (max-width: 380px) {
    .p_main-right {
      .block_payment {
        .system {
          width: 100%;
        }
      }
    }
  }
</style>

