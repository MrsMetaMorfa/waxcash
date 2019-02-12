<template>
  <div class="pagination container">
    <div class="pagination_prev container">
      <button class="btn btn-page" type="button">Первая</button>
      <button class="btn btn-page" type="button">&lt;</button>
    </div>
    <button class="btn btn-page" type="button">1</button>
    <button class="btn btn-page current" type="button">2</button>
    <button class="btn btn-page" type="button">3</button>
    <button class="btn btn-page" type="button">4</button>
    <button class="btn btn-page disabled" type="button">...</button>
    <button class="btn btn-page" type="button">12</button>
    <button class="btn btn-page" type="button">13</button>
    <button class="btn btn-page" type="button">14</button>
    <button class="btn btn-page" type="button">15</button>
    <div class="pagination_next container">
      <button class="btn btn-page" type="button">&gt;</button>
      <button class="btn btn-page" type="button">Последняя</button>
    </div>
  </div>
</template>

<script></script>

<style lang="less">
  .pagination {
    justify-content: center;
    align-items: center;
    width: 100%;
    padding-top: 15px;
    .btn {
      border-radius: 2px;
      background: #272938;
      padding: 10px;
      line-height: 16px;
      margin-left: 7px;
      margin-right: 7px;
      color: #777d97;
      margin-top: 14px;
      min-width: 36px;
      display: block;
      &:hover, &:focus {
        background: #0A0B0E;
      }
      &.current {
        background: #5499E8;
        color: white;
      }
      &.disabled {
        cursor: not-allowed;
        &:hover, &:focus {
          background: #272938;
        }
      }
    }
  }
</style>

