<template>
  <div class="wrapper">
    <!-- <nuxt/> - основной контент страницы -->
    <nuxt/>
  </div>
</template>

<script>

    export default {
        head: {
            link: [
                {rel: 'stylesheet', href: 'https://fonts.googleapis.com/css?family=Lato:100,100i,300,300i,400,400i,700,700i,900,900i'}
            ]
        },
        components: {}
    }
</script>

<style lang="less">
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-HeavyItalic.eot');
    src: local('SF UI Text Heavy Italic'), local('SFUIText-HeavyItalic'),
    url('~assets/fonts/SFUIText-HeavyItalic.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-HeavyItalic.woff') format('woff'),
    url('~assets/fonts/SFUIText-HeavyItalic.ttf') format('truetype');
    font-weight: 300;
    font-style: italic;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-LightItalic.eot');
    src: local('SF UI Text Light Italic'), local('SFUIText-LightItalic'),
    url('~assets/fonts/SFUIText-LightItalic.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-LightItalic.woff') format('woff'),
    url('~assets/fonts/SFUIText-LightItalic.ttf') format('truetype');
    font-weight: 300;
    font-style: italic;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-MediumItalic.eot');
    src: local('SF UI Text Medium Italic'), local('SFUIText-MediumItalic'),
    url('~assets/fonts/SFUIText-MediumItalic.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-MediumItalic.woff') format('woff'),
    url('~assets/fonts/SFUIText-MediumItalic.ttf') format('truetype');
    font-weight: 500;
    font-style: italic;
  }
  @font-face {
    font-family: 'SF UI Display';
    src: url('~assets/fonts/SFUIDisplay-Medium.eot');
    src: local('SF UI Display Medium'), local('SFUIDisplay-Medium'),
    url('~assets/fonts/SFUIDisplay-Medium.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIDisplay-Medium.woff') format('woff'),
    url('~assets/fonts/SFUIDisplay-Medium.ttf') format('truetype');
    font-weight: 500;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Display';
    src: url('~assets/fonts/SFUIDisplay-Regular.eot');
    src: local('SF UI Display Regular'), local('SFUIDisplay-Regular'),
    url('~assets/fonts/SFUIDisplay-Regular.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIDisplay-Regular.woff') format('woff'),
    url('~assets/fonts/SFUIDisplay-Regular.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Display';
    src: url('~assets/fonts/SFUIDisplay-Light.eot');
    src: local('SF UI Display Light'), local('SFUIDisplay-Light'),
    url('~assets/fonts/SFUIDisplay-Light.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIDisplay-Light.woff') format('woff'),
    url('~assets/fonts/SFUIDisplay-Light.ttf') format('truetype');
    font-weight: 300;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Display';
    src: url('~assets/fonts/SFUIDisplay-Thin.eot');
    src: local('SF UI Display Thin'), local('SFUIDisplay-Thin'),
    url('~assets/fonts/SFUIDisplay-Thin.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIDisplay-Thin.woff') format('woff'),
    url('~assets/fonts/SFUIDisplay-Thin.ttf') format('truetype');
    font-weight: 100;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Display';
    src: url('~assets/fonts/SFUIDisplay-Ultralight.eot');
    src: local('SF UI Display Ultralight'), local('SFUIDisplay-Ultralight'),
    url('~assets/fonts/SFUIDisplay-Ultralight.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIDisplay-Ultralight.woff') format('woff'),
    url('~assets/fonts/SFUIDisplay-Ultralight.ttf') format('truetype');
    font-weight: 100;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-Semibold.eot');
    src: local('SF UI Text Semibold'), local('SFUIText-Semibold'),
    url('~assets/fonts/SFUIText-Semibold.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-Semibold.woff') format('woff'),
    url('~assets/fonts/SFUIText-Semibold.ttf') format('truetype');
    font-weight: 600;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Display';
    src: url('~assets/fonts/SFUIDisplay-Semibold.eot');
    src: local('SF UI Display Semibold'), local('SFUIDisplay-Semibold'),
    url('~assets/fonts/SFUIDisplay-Semibold.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIDisplay-Semibold.woff') format('woff'),
    url('~assets/fonts/SFUIDisplay-Semibold.ttf') format('truetype');
    font-weight: 600;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-Regular.eot');
    src: local('SF UI Text Regular'), local('SFUIText-Regular'),
    url('~assets/fonts/SFUIText-Regular.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-Regular.woff') format('woff'),
    url('~assets/fonts/SFUIText-Regular.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Display';
    src: url('~assets/fonts/SFUIDisplay-Black.eot');
    src: local('SF UI Display Black'), local('SFUIDisplay-Black'),
    url('~assets/fonts/SFUIDisplay-Black.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIDisplay-Black.woff') format('woff'),
    url('~assets/fonts/SFUIDisplay-Black.ttf') format('truetype');
    font-weight: 300;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-BoldItalic.eot');
    src: local('SF UI Text Bold Italic'), local('SFUIText-BoldItalic'),
    url('~assets/fonts/SFUIText-BoldItalic.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-BoldItalic.woff') format('woff'),
    url('~assets/fonts/SFUIText-BoldItalic.ttf') format('truetype');
    font-weight: bold;
    font-style: italic;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-Bold.eot');
    src: local('SF UI Text Bold'), local('SFUIText-Bold'),
    url('~assets/fonts/SFUIText-Bold.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-Bold.woff') format('woff'),
    url('~assets/fonts/SFUIText-Bold.ttf') format('truetype');
    font-weight: bold;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Display';
    src: url('~assets/fonts/SFUIDisplay-Heavy.eot');
    src: local('SF UI Display Heavy'), local('SFUIDisplay-Heavy'),
    url('~assets/fonts/SFUIDisplay-Heavy.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIDisplay-Heavy.woff') format('woff'),
    url('~assets/fonts/SFUIDisplay-Heavy.ttf') format('truetype');
    font-weight: 900;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-Light.eot');
    src: local('SF UI Text Light'), local('SFUIText-Light'),
    url('~assets/fonts/SFUIText-Light.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-Light.woff') format('woff'),
    url('~assets/fonts/SFUIText-Light.ttf') format('truetype');
    font-weight: 300;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-Heavy.eot');
    src: local('SF UI Text Heavy'), local('SFUIText-Heavy'),
    url('~assets/fonts/SFUIText-Heavy.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-Heavy.woff') format('woff'),
    url('~assets/fonts/SFUIText-Heavy.ttf') format('truetype');
    font-weight: 900;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-Medium.eot');
    src: local('SF UI Text Medium'), local('SFUIText-Medium'),
    url('~assets/fonts/SFUIText-Medium.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-Medium.woff') format('woff'),
    url('~assets/fonts/SFUIText-Medium.ttf') format('truetype');
    font-weight: 500;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Display';
    src: url('~assets/fonts/SFUIDisplay-Bold.eot');
    src: local('SF UI Display Bold'), local('SFUIDisplay-Bold'),
    url('~assets/fonts/SFUIDisplay-Bold.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIDisplay-Bold.woff') format('woff'),
    url('~assets/fonts/SFUIDisplay-Bold.ttf') format('truetype');
    font-weight: bold;
    font-style: normal;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-Italic.eot');
    src: local('SF UI Text Italic'), local('SFUIText-Italic'),
    url('~assets/fonts/SFUIText-Italic.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-Italic.woff') format('woff'),
    url('~assets/fonts/SFUIText-Italic.ttf') format('truetype');
    font-weight: normal;
    font-style: italic;
  }
  @font-face {
    font-family: 'SF UI Text';
    src: url('~assets/fonts/SFUIText-SemiboldItalic.eot');
    src: local('SF UI Text Semibold Italic'), local('SFUIText-SemiboldItalic'),
    url('~assets/fonts/SFUIText-SemiboldItalic.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/SFUIText-SemiboldItalic.woff') format('woff'),
    url('~assets/fonts/SFUIText-SemiboldItalic.ttf') format('truetype');
    font-weight: 600;
    font-style: italic;
  }
  @font-face {
    font-family: 'MarkPro';
    src: url('~assets/fonts/Mark-Bold.eot');
    src: local('Mark-Bold'), local('Mark-Bold'),
    url('~assets/fonts/Mark-Bold.eot?#iefix') format('embedded-opentype'),
    url('~assets/fonts/Mark-Bold.woff') format('woff'),
    url('~assets/fonts/Mark-Bold.ttf') format('truetype');
    font-weight: 700;
    font-style: normal;
  }

  html {
    font-family: "SF UI Display", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    font-size: 16px;
    line-height: 1.2;
    word-spacing: 1px;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
    overflow-x: hidden;
  }
  *, *:before, *:after {
    box-sizing: border-box;
    margin: 0;
    transition: all 0.25s ease-in;
  }
  *::selection {
    color: inherit;
    background: rgba(0,0,0,0.05);
  }

  body {
    background: #0c0d10;
    width: 100%;
    margin: -1px 0 0;
    padding: 1px 0 0;
    min-height: 100vh;
    color: white;
    overflow-x: hidden;
  }
  .page {
    min-height: 100vh;
    padding-top: 80px;
  }
  .translated {
    transform: translateX(300px);
  }
  .container {
    display: flex;
    &--justify {
      justify-content: space-between;
    }
  }
  a, button, input, textarea {
    &:hover, &:focus, &:active, &:visited {
      outline: none;
    }
  }
  img {
    display: block;
    margin: 0;
    max-width: 100%;
  }
  .p_container {
    min-height: calc(100vh - 80px);
    padding: 14px;
    position: relative;
  }
  .block {
    border-radius: 2px;
    background-color: rgb(22, 23, 31);
    &_light {
      border-radius: 2px;
      background-color: rgb(39, 41, 56);
    }
  }
  .btn {
    color: inherit;
    border: none;
    border-radius: 0;
    background: transparent;
    padding: 0;
    cursor: pointer;
  }
  .angle {
    display: inline-block;
    width: 10px;
    height: 10px;
    margin: 5px;
    border: solid #777D97;
    border-width: 0 1px 1px 0;
    transform: rotate(45deg);
  }
  .btn-huge {
    border-radius: 2px;
    background: #38D75A;
    padding: 14px;
    text-transform: uppercase;
    width: 222px;
    min-height: 41px;
    align-items: center;
    justify-content: center;
    border: 1px solid #38D75A;
    img {
      margin-left: 14px;
      height: 21px;
    }
    &:hover, &:focus {
      background: transparent;
    }
  }
  .btn-bright {
    border-radius: 3px;
    background-color: #5499E8;
    padding: 8px 29px 6px;
    text-transform: uppercase;
    font-weight: 700;
    font-size: 18px;
    height: auto;
    &:hover, &:focus {
      background: #16171F;
    }
  }
  .btn-dark {
    border-radius: 3px;
    background-color: #272938;
    padding: 8px 29px 6px;
    height: auto;
    &:hover, &:focus {
      background: #5499E8;
    }
  }
  .form_line {
    width: 100%;
    label {
      display: block;
      margin-bottom: 14px;
    }
  }
  .input_wrapper {
    position: relative;
    margin-bottom: 14px;
    &.correct {
      input {
        padding-right: 30px;
        &:hover, &:focus {
          border-color: rgb(56, 223, 90);
          border-image: none;
        }
      }
      &:after {
        content: url("~assets/images/check.png");
        display: block;
        border-radius: 50%;
        background-color: rgba(56, 223, 90, 0.15);
        position: absolute;
        width: 20px;
        height: 20px;
        color: rgb(56, 223, 90);
        top: 50%;
        margin-top: -10px;
        right: 16px;
        z-index: 1;
        text-align: center;
      }
    }
    &.error {
      input {
        padding-right: 30px;
        border-color: #e22e2f;
        &:hover, &:focus {
          border-image: none;
          box-shadow: 0 0 0 2px #e22e2f;
        }
      }
      &:after {
        content: url("~assets/images/wrong.png");
        display: block;
        border-radius: 50%;
        background-color: rgba(182, 25, 27, 0.15);
        position: absolute;
        width: 20px;
        height: 20px;
        color: #e22e2f;
        top: 50%;
        margin-top: -10px;
        right: 16px;
        z-index: 1;
        text-align: center;
      }
    }
    input, textarea, select {
      display: block;
      width: 100%;
      border-radius: 2px;
      background-color: rgb(39, 41, 56);
      padding: 12px 14px;
      line-height: 1.75;
      min-height: 50px;
      color: white;
      position: relative;
      z-index: 1;
      border: 2px solid transparent;
      border-image: none;
      &:hover, &:focus {
        outline: none;
        border-image: linear-gradient(to right, rgba(8, 174, 234, 1) 0%, rgba(42, 245, 152, 1) 100%);
        border-image-slice: 1;
      }
    }
  }

</style>

