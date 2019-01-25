<template>
  <div class="block aside_news">
    <ul>
      <li class="container container--justify news">
        <div class="image">
          <img src="~assets/images/news-1.jpg" alt="">
        </div>
        <p>
          <strong>Редизайн нашего сайта</strong><br>
          <data>26 декабря 2019</data>
        </p>
        <button class="btn btn-more"><span class="angle"></span></button>
      </li>
      <li class="container container--justify news">
        <div class="image">
          <img src="~assets/images/news-1.jpg" alt="">
        </div>
        <p>
          <strong>Редизайн нашего сайта</strong><br>
          <data>26 декабря 2019</data>
        </p>
        <button class="btn btn-more"><span class="angle"></span></button>
      </li>
      <li class="container container--justify news">
        <div class="image">
          <img src="~assets/images/news-1.jpg" alt="">
        </div>
        <p>
          <strong>Редизайн нашего сайта</strong><br>
          <data>26 декабря 2019</data>
        </p>
        <button class="btn btn-more"><span class="angle"></span></button>
      </li>
      <li class="container container--justify news">
        <div class="image">
          <img src="~assets/images/news-1.jpg" alt="">
        </div>
        <p>
          <strong>Редизайн нашего сайта</strong><br>
          <data>26 декабря 2019</data>
        </p>
        <button class="btn btn-more"><span class="angle"></span></button>
      </li>
      <li class="container container--justify news">
        <div class="image">
          <img src="~assets/images/news-1.jpg" alt="">
        </div>
        <p>
          <strong>Редизайн нашего сайта</strong><br>
          <data>26 декабря 2019</data>
        </p>
        <button class="btn btn-more"><span class="angle"></span></button>
      </li>
    </ul>
  </div>
</template>

<style lang="less">
  .aside_news {
    width: 100%;
    padding: 29px;
    height: calc(50% - 14px);
    min-height: 375px;
    ul {
      padding: 0;
      list-style-type: none;
      li {
        align-items: center;
        &:not(:last-of-type) {
          margin-bottom: 14px;
        }
        .image {
          border-radius: 3px;
          overflow: hidden;
          width: 52px;
          height: 52px;
          img {
            display: block;
            margin: 0;
          }
        }
        p {
          color: #777d97;
          width: calc(100% - 80px);
          padding: 0 14px;
          font-size: 10px;
          line-height: 1.4;
          strong {
            color: white;
            font-size: 13px;
          }
        }
        .btn {
          border-radius: 4px;
          background-color: rgb(39, 41, 56);
          padding: 17px 2px 17px 0;
          height: 52px;
          width: 28px;
          .angle {
            transform: rotate(-45deg);
          }
        }
      }
    }
  }
  @media screen and (max-width: 2048px) {
    .aside_news {
      height: calc(100% - 584px);
    }
  }
  @media screen and (max-width: 1824px) {
    .aside_news {
      width: 25%;
      height: 100%;
    }
  }
  @media screen and (max-width: 1160px) {
    .aside_news {
      width: 33%;
      height: 428px;
    }
  }
  @media screen and (max-width: 900px) {
    .aside_news {
      width: 100%;
      margin: 0;
      height: auto;
      min-height: auto;
      ul {
        display: flex;
        flex-wrap: wrap;
        li {
          width: calc(100%/3 - 14px);
          margin: 0 7px 14px;
        }
      }
    }
  }
  @media screen and (max-width: 767px) {
    .aside_news {
      ul {
        li {
          width: calc(50% - 14px);
        }
      }
    }
  }
  @media screen and (max-width: 560px) {
    .aside_news {
      ul {
        li {
          max-width: 320px;
          width: 100%;
          margin: 0 auto 14px;
        }
      }
    }
  }
</style>

