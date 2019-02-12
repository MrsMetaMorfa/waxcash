<template>
  <form class="help block" id="modalHelp">
    <button class="btn btn-close" type="button"
            onclick="this.parentNode.parentNode.classList.remove('active');
            this.parentNode.classList.remove('active');"
    >
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 140 139.9">
        <title>Закрыть</title>
        <path d="M3.4,136.6C-.4,132.8-1,129,1.6,125c.9-1.4,13.4-14.3,27.8-28.8L55.5,70,29.4,43.7C15,29.3,2.5,16.4,1.6,15-1,11-.4,7.2,3.4,3.4S11-1,15,1.6c1.4.9,14.3,13.4,28.7,27.8L70,55.5,96.2,29.4C110.7,15,123.6,2.5,125,1.6c4-2.6,7.8-2,11.6,1.8S141,11,138.4,15,21.2,133.6,16.6,137.1s-8.9,3.8-13.2-.5Zm120,.5c-4.6-3.4-34.4-33.4-36.8-37.1s-2-7.8,1.8-11.6S96,84,100,86.6s33.7,32.2,37.1,36.8,3.8,8.9-.5,13.2-7.9,4.4-13.2.5Z"/>
      </svg>
    </button>
    <h2>Помощь</h2>
    <p>Выберите удобный вам способ</p>
    <div class="help_type container">
      <div class="help_type-item">
        <input type="radio" name="helpType" id="helpTypeVk" value="ВКонтакте" checked>
        <label for="helpTypeVk">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1112.6 632.5">
            <title>VKontakte</title>
            <path d="M885.4,630.6c-19.2-4.5-45.7-19.2-62.9-34.9-8.6-7.9-30.4-30.9-48.4-51-57.3-64.2-75.3-72.3-99.6-44.7-14.7,16.7-20.8,37.8-24.1,83.4-1.9,26.3-3.9,31.2-16.4,40.5-5.5,4.1-10.1,4.6-55.3,5.8-75.3,2.1-109.5-2.7-158.1-22.2-43.2-17.3-103.6-57.3-140.9-93.1-48.4-46.6-121.4-148-174.1-241.6C61.8,194.9,2.7,72.4.2,54.7c-1.3-9.8,3-17.3,13.1-22.8,6.4-3.5,15.8-3.9,96.1-4.6s90-.2,98.5,3c15.4,5.9,21.1,12.3,31.2,35.3,27.8,63.6,73.2,151.3,96.6,186.5,30.4,45.7,60.9,66.9,78.6,54.5,16-11.2,25.9-68.5,24-139.3C436.1,82,425.2,57.8,384,46.5c-8.3-2.3-13.7-5-14.1-7.1s3.6-7.5,8.7-12.5C400.8,5.1,426.9,0,516.3,0c99.8,0,121.1,5.9,131.8,36.7,2.5,7,3.1,31.3,3.1,124,0,113,.1,115.5,4.6,125.3,6.5,14,15.2,21.6,24.8,21.6,6.2,0,10.7-2.4,21.8-11.6,16.5-13.6,26.7-25.5,46.1-53.7,35.3-51.4,62.1-100,87.4-158.8,17.6-40.8,21.5-47.5,29.7-51.4,3.7-1.8,38-2.8,115.1-3.3l109.9-.8,9.1,4.9c18.3,9.8,17.2,31.5-3.5,72.7-16,31.6-41.7,69.5-98.9,145.4-28.4,37.7-54.7,74.8-58.5,82.4-8.1,16.5-8.5,30.1-1.3,44.4,2.9,5.7,25.9,30.3,61.6,65.7,58.8,58.4,74.4,75.9,95.5,107.8,13.7,20.6,19.6,40.1,16.4,54.2-2,8.8-12.4,18.5-23.7,21.9-14.7,4.5-184.8,7.1-201.9,3.2Z"/>
          </svg>
          <span>ВКонтакте</span>
        </label>
      </div>
      <div class="help_type-item">
        <input type="radio" name="helpType" id="helpTypeChat" value="Чат на сайте">
        <label for="helpTypeChat">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 219.6 179.6">
            <title>Chat</title>
            <path d="M3.4,176.2,0,172.8V56.4L3.4,53c2.3-2.3,4.3-3.4,6.4-3.4s13.7,6.8,41.5,24.1l38.5,24,28.6-19c32-21.3,32.4-21.4,38.2-15.7,4,4.1,4.4,8,1.2,12.1s-64.4,44.5-67.7,44.5-12.6-5.9-61.8-36.8L20,77.6v82H180V58l-3.4-1.6a29.9,29.9,0,0,1-12.7-12.2l-2.4-4.6H26.8l-3.4-3.4c-2.5-2.4-3.4-4.3-3.4-6.6s.9-4.1,3.4-6.6l3.4-3.4H161.5L164,15c8.9-16.9,33.2-20.2,47-6.4s10.6,38.1-6.4,47.1L200,58.1V172.8l-3.4,3.4-3.4,3.4H6.8Zm191.5-138c4.7-2.5,6.3-8.3,3.7-13.4-3.5-6.7-13.7-6.7-17.2,0C176.7,33.9,185.8,42.9,194.9,38.2Z"/>
          </svg>
          <span>Чат на сайте</span>
        </label>
      </div>
    </div>
    <div class="hint container">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1039 1039.6">
        <title>info-full</title>
        <path d="M480.8,1038.9c-104.4-9.7-194.6-43.9-276-104.7-25.6-19.1-80.8-74.4-100-100C61,775.5,30.5,711.3,14,642.6,2.8,596.2,0,571.3,0,519.5s2.8-76.6,14-123c16.5-68.7,47-132.9,90.8-191.6,19.2-25.6,74.4-80.9,100-100C277.6,50.6,356.9,17.7,449.7,3.6c31.5-4.8,107.1-4.8,139.9,0,90.6,13.3,171.9,47,244.5,101.3,25.7,19.1,80.9,74.4,100,100,54.4,72.7,87.2,152.1,101.3,244.9,4.8,31.5,4.8,107.1,0,139.9-8.3,56.2-24.3,108.5-48.1,157.3-27.4,56.1-54.1,93.2-100.6,139.7S803,960,746.9,987.4a526.2,526.2,0,0,1-156.2,47.8c-22.5,3.2-90.9,5.5-109.9,3.7ZM548,807.1c14.4-6.6,29-22,34.4-36.6,4.1-10.8,4.2-14.9,4.2-160.4s-.1-149.6-4.2-160.7c-4.9-12.9-19.2-28.9-31.6-35.2-18.6-9.5-44.1-9.5-62.6,0-12.4,6.3-26.8,22.3-31.6,35.2-4.2,11.1-4.2,14.5-4.2,160.7s.1,149.6,4.1,160.4c5,13.3,19.5,29.4,32.1,35.7,18.7,9.4,39.8,9.7,59.4.9Zm-.9-454.6c39.4-14.6,50.2-69.4,19.6-100.4-23.1-23.4-67.2-24.3-93.8-1.9-17.1,14.4-23.9,48.7-14,70.3,6.7,14.7,13.5,22.2,25.9,29,18.2,9.9,40.8,11,62.3,3Z"/>
      </svg>
      <p>Наши операторы ответят вам в течении <span>24</span>
        часов и обязательно помогут решить проблему</p>
    </div>
    <button class="btn btn-huge" type="submit">Написать</button>
  </form>
</template>

<script></script>

<style lang="less">
  .help {
    display: none;
    padding: 65px 70px 70px;
    text-align: center;
    max-width: 618px;
    position: relative;
    margin: auto!important;
    background-image: linear-gradient(to right, #184e68, #57CA85);
    background-repeat: no-repeat;
    background-position: center bottom;
    background-size: 100% 5px;
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
    h2 {
      font-size: 33px;
      margin-bottom: 14px;
    }
    p {
      font-size: 20px;
      margin-bottom: 29px;
      color: #777d97;
    }
    .hint {
      align-items: center;
      margin-top: 20px;
      margin-bottom: 20px;
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
    }
    &_type {
      justify-content: center;
      &-item {
        padding: 0 7px 14px;
        width: 50%;
        max-width: 238px;
        input {
          width: 0;
          height: 0;
          visibility: hidden;
          position: absolute;
          opacity: 0;
        }
        label {
          width: 100%;
          border-radius: 2px;
          background-color: rgb(39, 41, 56);
          padding: 14px 58px;
          display: flex;
          align-items: center;
          justify-content: center;
          flex-direction: column;
          cursor: pointer;
          position: relative;
          color: #777d97;
          svg {
            margin: 0 auto 14px;
            width: auto;
            height: 28px;
            path {
              fill: #777d97;
            }
          }

        }
        input:checked + label, label:hover {
          color: white;
          svg path {
            fill: white;
          }
        }
        input:checked + label {
          background-image: linear-gradient(45deg, #184e68, #57ca85);
          &:after {
            content: url("~assets/icons/check-mark-01-01.svg");
            display: block;
            border-radius: 50%;
            background: white;
            width: 22px;
            height: 22px;
            position: absolute;
            right: 19px;
            top: 50%;
            margin-top: -11px;
            padding: 3px 4px;
          }
        }
      }
    }
    &.active {
      display: block;
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
      &_type {
        flex-wrap: wrap;
        &-item {
          width: 100%;
          margin: 0 auto 14px;
          label {
            padding-left: 29px;
          }
        }
      }
    }
  }
</style>

