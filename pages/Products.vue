<template>
  <div class="Products">
    <h1 class="Products__title">{{ $t('products.heading1') }} <img src="../assets/img/products/kreditomat-txt.png" alt=""></h1>
    <div class="custom_border"/>
    <div class="welcome_img">
      <div class="app">
        <img src="../assets/img/products/app.png"/>
        <div class="app__links">
          <img src="../assets/img/products/apple.png"/>
          <img src="../assets/img/products/market.png"/>
        </div>
      </div>
      <img src="../assets/img/products/circles.png" v-if="$i18n.locale === 'ru'"/>
      <img src="../assets/img/products/circles-en.png" v-else>
    </div>
    <div class="advantages">
      <h2>{{ $t('products.advOfAppTitle') }}</h2>
      <div class="advantages__grid">
        <div class="advantages__grid__single">
          <h3>{{ $t('products.featureTitle1') }}</h3>
          <div class="grid_border"/>
          <p v-html="$t('products.featureText1')"></p>
        </div>
        <div class="advantages__grid__single">
          <h3 v-html="$t('products.featureTitle2')"></h3>
          <div class="grid_border"/>
          <p v-html="$t('products.featureText2')"></p>
        </div>
        <div class="advantages__grid__single">
          <h3>{{ $t('products.featureTitle3') }}</h3>
          <div class="grid_border"/>
          <p v-html="$t('products.featureText3')"></p>
        </div>
      </div>
    </div>
    <div class="sup_txt">
      <div class="sup_txt__content">
        <div class="image_wrapper">
          <img src="../assets/img/products/time.png"/>
        </div>
        <p v-html="$t('products.timingFeature')"></p>
        <div class="image_wrapper">
          <img src="../assets/img/products/coins.png"/>
        </div>
      </div>
    </div>
    <div class="terminal">
      <h1>
        {{ $t('products.heading2') }} <img src="../assets/img/products/kreditomat-txt.png" alt="">
      </h1>
      <div class="custom_border"/>
      <img class="terminal__image" src="../assets/img/products/terminal.png" v-if="$i18n.locale === 'ru'"/>
      <img class="terminal__image" src="../assets/img/products/terminal-en.png" v-else/>
    </div>
    <div class="term_adv">
      <h2>{{ $t('products.advOfAlmTitle') }}</h2>
      <div class="term_adv__grid">
        <div class="term_adv__grid__single">
          <img src="../assets/img/products/eye.png"/>
          <p>
            {{ $t('products.itemText1') }}
          </p>
        </div>
        <div class="term_adv__grid__single">
          <img src="../assets/img/products/shop_hand.png"/>
          <p>
            {{ $t('products.itemText2') }}
          </p>
        </div>
        <div class="term_adv__grid__single">
          <img src="../assets/img/products/money_hand.png"/>
          <p>
            {{ $t('products.itemText3') }}
          </p>
        </div>
        <div class="term_adv__grid__single">
          <img src="../assets/img/products/tv.png"/>
          <p>
            {{ $t('products.itemText4') }}
          </p>
        </div>
        <div class="term_adv__grid__single">
          <img src="../assets/img/products/criminal.png"/>
          <p>
            {{ $t('products.itemText5') }}
          </p>
        </div>
        <div class="term_adv__grid__single">
          <img src="../assets/img/products/debit_cart.png"/>
          <p>
            {{ $t('products.itemText6') }}
          </p>
        </div>
      </div>
    </div>
    <div class="dbl_terminal">
      <img src="../assets/img/products/dbl_terminal.png"/>
      <div class="dbl_terminal__txt">
        <h2>{{ $t('products.requireTerminalTitle') }}</h2>
        <div class="cus_brd"/>
        <p>{{ $t('products.require1') }}</p>
        <p>{{ $t('products.require2') }}</p>
        <p>{{ $t('products.require3') }}</p>
        <p>{{ $t('products.require4') }}</p>
        <p>{{ $t('products.require5') }}</p>
      </div>
    </div>
    <div class="atm_txt">
      <div class="atm_txt__content">
        <img src="../assets/img/products/atm.png"/>
        <div>
          <p v-html="$t('products.fluidText1')"></p>
          <p v-html="$t('products.fluidText2')"></p>
          <p v-html="$t('products.fluidText3')"></p>
        </div>
      </div>
    </div>
    <div class="click_adv">
      <h1>
        {{ $t('products.heading3') }} <img src="../assets/img/products/click-logo.png" alt="">
      </h1>
      <div class="custom_border"/>
      <div class="welcome_img">
        <div class="app">
          <img src="../assets/img/products/app2.png"/>
          <div class="app__links">
            <img src="../assets/img/products/apple.png"/>
            <img src="../assets/img/products/market.png"/>
          </div>
        </div>
        <img src="../assets/img/products/steps.png" v-if="$i18n.locale === 'ru'"/>
        <img src="../assets/img/products/steps-en.png" v-else/>
      </div>
      <div class="adv_click">
        <h2>
          {{ $t('products.advOfClickTitle') }}
        </h2>
        <div class="adv_click__grid">
          <div class="adv_click__grid__single">
            <img src="../assets/img/products/handshake.png"/>
            <p v-html="$t('products.itemText7')"></p>
          </div>
          <div class="adv_click__grid__single">
            <img src="../assets/img/products/piechart.png"/>
            <p v-html="$t('products.itemText8')"></p>
          </div>
          <div class="adv_click__grid__single">
            <img src="../assets/img/products/regression.png"/>
            <p v-html="$t('products.itemText9')"></p>
          </div>
          <div class="adv_click__grid__single">
            <img src="../assets/img/products/money_talk.png"/>
            <p v-html="$t('products.itemText10')"></p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";

.Products {
  padding-top: 130px;

  &__title {
    display: flex;
    justify-content: center;
    align-items: center;
    @include bold;
    font-size: 40px;
    line-height: 47px;
    text-align: center;
    text-transform: uppercase;
    color: #623f99;

    img {
      margin-left: 30px;
    }
  }
}

.custom_border {
  width: 160px;
  border-bottom: 2px solid #623f99;
  margin: 10px auto 60px;
}

.welcome_img {
  display: flex;
  align-items: center;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;

  .app {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-right: 52px;

    &__links {
      margin-top: 22px;

      img:first-of-type {
        margin-right: 20px;
      }
    }
  }
}

.advantages {
  padding: 60px 0;

  h2 {
    @include bold;
    font-size: 24px;
    line-height: 30px;
    text-align: center;
    text-transform: uppercase;
    color: #d5dd25;
    margin-bottom: 30px;
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(3, 387px);
    justify-content: space-between;
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;

    &__single {
      height: 174px;
      background: #ffffff;
      box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
      border-radius: 4px;
      text-align: center;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      h3 {
        @include bold;
        font-size: 24px;
        line-height: 30px;
        text-transform: uppercase;
        color: #623f99;
      }

      .grid_border {
        width: 70px;
        border-bottom: 1px solid #623f99;
        margin: 10px auto;
      }

      p {
        @include normal;
        font-size: 16px;
        line-height: 20px;
        color: #131313;
      }
    }
  }
}

.sup_txt {
  background: #623F99;
  height: 140px;
  padding-top: 20px;

  &__content {
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;

    p {
      @include normal;
      font-size: 16px;
      line-height: 19px;
      text-align: center;
      text-transform: uppercase;
      color: #FFFFFF;
      max-width: 965px;
    }
  }

  .image_wrapper {
    display: flex;
    justify-content: flex-start;
    align-items: center;

    &:last-of-type {
      justify-content: flex-end !important;
    }
  }
}

.terminal {
  padding-top: 120px;
  padding-bottom: 60px;
  text-align: center;
  background-color: #F8F2FF;

  h1 {
    display: flex;
    justify-content: center;
    @include bold;
    font-size: 40px;
    line-height: 47px;
    text-transform: uppercase;
    color: #623f99;

    img {
      margin-left: 30px;
    }
  }

  &__image {
    margin-top: -80px;
  }
}

.term_adv {
  padding-bottom: 60px;
  background-color: #F8F2FF;

  h2 {
    @include bold;
    font-size: 24px;
    line-height: 28px;
    text-align: center;
    text-transform: uppercase;
    color: #d5dd25;
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(3, 387px);
    justify-content: space-between;
    grid-row-gap: 20px;
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;
    padding-top: 30px;

    &__single {
      height: 237px;
      background: #ffffff;
      box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
      border-radius: 8px;
      padding: 30px;
      text-align: center;

      p {
        @include normal;
        font-size: 16px;
        line-height: 19px;
        color: #131313;
        margin-top: 27px;
      }
    }
  }
}

.dbl_terminal {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding-bottom: 60px;
  background-color: #F8F2FF;

  img {
    margin-right: 79px;
  }

  &__txt {
    h2 {
      @include bold;
      font-size: 24px;
      line-height: 28px;
      text-transform: uppercase;
      color: #623f99;
    }

    .cus_brd {
      width: 160px;
      border-bottom: 2px solid #623f99;
      margin-top: 10px;
      margin-bottom: 38px;
    }

    p {
      position: relative;
      @include normal;
      font-size: 18px;
      line-height: 21px;
      color: #131313;
      margin-bottom: 21px;
      margin-left: 39px;

      &::after {
        content: url("../assets/img/main/checkbox.png");
        position: absolute;
        top: 2px;
        left: -39px;
      }

      &:last-of-type {
        margin-bottom: 0;
      }
    }
  }
}

.atm_txt {
  background: #623F99;
  height: 180px;
  padding-top: 30px;

  &__content {
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;
    display: flex;
    align-items: flex-start;

    img {
      margin-right: 60px;
    }

    p {
      @include normal;
      font-size: 16px;
      line-height: 20px;
      text-transform: uppercase;
      color: #FFFFFF;

      &:nth-child(2) {
        margin: 10px 0;
      }
    }
  }
}

.click_adv {
  padding: 120px 0;
  background-image: url("../assets/img/products/click_adv-bg.png");
  background-size: cover;
  background-position-y: -2px;

  h1 {
    display: flex;
    justify-content: center;
    align-items: center;
    @include bold;
    font-size: 40px;
    line-height: 47px;
    text-align: center;
    text-transform: uppercase;
    color: #623f99;

    img {
      margin-left: 30px;
    }
  }
}

.adv_click {
  padding-top: 60px;

  h2 {
    @include bold;
    font-size: 24px;
    line-height: 28px;
    text-align: center;
    text-transform: uppercase;
    color: #623F99;
    margin-bottom: 30px;
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(4, 285px);
    justify-content: space-between;
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;

    &__single {
      background: #ffffff;
      box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
      border-radius: 4px;
      //height: 255px;
      padding: 30px 20px 20px;
      text-align: center;

      p {
        @include normal;
        font-size: 16px;
        line-height: 20px;
        color: #131313;
      }

      img {
        margin-bottom: 20px;
      }
    }
  }
}
</style>

<style>
.sup_txt .sup_txt__content p span {
  color: #d5dd25;
}
</style>
