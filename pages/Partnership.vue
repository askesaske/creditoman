<template>
  <div class="partners">
    <a class="partners__btn"
            :class="btnStop ? 'partners__btn--stop' : ''"
            href="http://185.100.65.231/api/download/">
      {{ $t('partnership.download') }} <img src="../assets/img/about/drop.png"/>
    </a>
    <div class="partner-welcome">
      <div class="partner-welcome__inner">
        <p>
          {{ $t('partnership.welcomeText1') }}
        </p>
        <p>
          {{ $t('partnership.welcomeText2') }}
        </p>
        <p>
          {{ $t('partnership.welcomeText3') }}
        </p>
      </div>
    </div>

    <div class="terms">
      <h1 class="title">{{ $t('partnership.coopHeading') }}</h1>
      <div class="custom_border"/>
      <p class="title_txt">
        {{ $t('partnership.coopText') }}
      </p>
      <div class="who_people">
        <div class="who_people__box">
          <div class="vertical_txt">
            <p>{{ $t('partnership.thoseWho') }}</p>
          </div>
          <div class="normal_txt">
            <p v-html="$t('partnership.coopItemText1')"></p>
            <img src="../assets/img/partnership/cogs.png"/>
          </div>
        </div>
        <!--        <div class="empty_for_verstka"/>-->
      </div>
      <div class="who_people">
        <div class="empty_for_verstka"/>
        <div class="who_people__box">
          <div class="normal_txt normal_txt--reverse">
            <img src="../assets/img/partnership/global.png"/>
            <p style="text-align: right" v-html="$t('partnership.coopItemText2')"></p>
          </div>
          <div class="vertical_txt left_side">
            <p>{{ $t('partnership.thoseWho') }}</p>
          </div>
        </div>
      </div>
      <div class="who_people">
        <div class="who_people__box">
          <div class="vertical_txt">
            <p>{{ $t('partnership.thoseWho') }}</p>
          </div>
          <div class="normal_txt">
            <p style="text-align: left" v-html="$t('partnership.coopItemText3')"></p>
            <img src="../assets/img/partnership/handshake.png"/>
          </div>
        </div>
        <!--        <div class="empty_for_verstka"/>-->
      </div>
    </div>

    <div class="statistics">
      <div class="statistics__content">
        <img src="../assets/img/partnership/percentage.png"/>
        <div class="statistics__content__txt">
          <p v-html="$t('partnership.fluidText1')"></p>
          <p v-html="$t('partnership.fluidText2')"></p>
          <p v-html="$t('partnership.fluidText3')"></p>
        </div>
        <img src="../assets/img/products/coins.png"/>
      </div>
    </div>
    <div class="howto">
      <h2>{{ $t('partnership.modelHeading') }}</h2>
      <img class="howto__step-img" src="../assets/img/partnership/howto.png" v-if="$i18n.locale === 'ru'"/>
      <img class="howto__step-img" src="../assets/img/partnership/howto-en.png" v-else/>

      <div class="welcome_img">
        <div class="welcome_img__mobile-circles">
          <div class="welcome_img__mobile-step">
            <img src="../assets/img/partnership/bModel1.png" alt="">
            <p>{{ $t('partnership.bModel1')}}</p>
          </div>
          <div class="welcome_img__mobile-step">
            <img src="../assets/img/partnership/bModel2.png" alt="">
            <p>{{ $t('partnership.bModel2')}}</p>
          </div>
          <div class="welcome_img__mobile-step">
            <img src="../assets/img/partnership/bModel3.png" alt="">
            <p>{{ $t('partnership.bModel3')}}</p>
          </div>
          <div class="welcome_img__mobile-step">
            <img src="../assets/img/partnership/bModel4.png" alt="">
            <p>{{ $t('partnership.bModel4')}}</p>
          </div>
          <div class="welcome_img__mobile-step">
            <img src="../assets/img/partnership/bModel5.png" alt="">
            <p>{{ $t('partnership.bModel5')}}</p>
          </div>
          <div class="welcome_img__mobile-step">
            <img src="../assets/img/partnership/bModel6.png" alt="">
            <p>{{ $t('partnership.bModel6')}}</p>
          </div>
          <div class="welcome_img__mobile-step">
            <img src="../assets/img/partnership/bModel7.png" alt="">
            <p>{{ $t('partnership.bModel7')}}</p>
          </div>
        </div>
      </div>

      <h1 class="title">{{ $t('partnership.benefitHeading') }}</h1>
      <div class="custom_border"/>
      <div class="model_types">
        <div class="model_types__single">
          <div class="model_title first_model_title">
            <h2 v-html="$t('partnership.modelBoxTitle1')"></h2>
          </div>
          <div class="model_descr">
            <p v-html="$t('partnership.modelBoxText1')"></p>
            <p v-html="$t('partnership.modelBoxText2')"></p>
            <p v-html="$t('partnership.modelBoxText3')"></p>
          </div>
        </div>
        <div class="model_types__single">
          <div class="model_title second_model_title">
            <h2 v-html="$t('partnership.modelBoxTitle2')"></h2>
          </div>
          <div class="model_descr">
            <p v-html="$t('partnership.modelBoxText4')"></p>
            <p v-html="$t('partnership.modelBoxText5')"></p>
            <p v-html="$t('partnership.modelBoxText6')"></p>
            <p v-html="$t('partnership.modelBoxText7')"></p>
          </div>
        </div>
        <div class="model_types__single">
          <div class="model_title third_model_title">
            <h2 v-html="$t('partnership.modelBoxTitle3')"></h2>
          </div>
          <div class="model_descr">
            <p v-html="$t('partnership.modelBoxText8')"></p>
            <p v-html="$t('partnership.modelBoxText9')"></p>
            <p v-html="$t('partnership.modelBoxText10')"></p>
            <p v-html="$t('partnership.modelBoxText11')"></p>
          </div>
        </div>
      </div>

    </div>

    <div class="download_ques">
      <p v-html="$t('partnership.fluidHeading')"></p>
      <a href="http://185.100.65.231/api/download/" class="partners__btn download_ques__btn">
        {{ $t('partnership.download') }} <img src="../assets/img/about/drop.png"/>
      </a>
    </div>

    <h1 class="title">{{ $t('partnership.costHeading') }}</h1>
    <div class="custom_border"/>
    <p class="costs_txt" v-html="$t('partnership.costText')"></p>
    <div class="cost_grid">
      <div class="cost_grid__single">
        <img src="../assets/img/partnership/1.png"/>
        <p>
          {{ $t('partnership.costBoxTitle1') }}
        </p>
      </div>
      <div class="cost_grid__single">
        <img src="../assets/img/partnership/2.png"/>
        <p>
          {{ $t('partnership.costBoxTitle2') }}
        </p>
      </div>
      <div class="cost_grid__single">
        <img src="../assets/img/partnership/3.png"/>
        <p v-html="$t('partnership.costBoxTitle3')"></p>
      </div>
      <div class="cost_grid__single">
        <img src="../assets/img/partnership/4.png"/>
        <p>
          {{ $t('partnership.costBoxTitle4') }}
        </p>
      </div>
      <div class="cost_grid__single">
        <img src="../assets/img/partnership/6.png"/>
        <p>
          {{ $t('partnership.costBoxTitle5') }}
        </p>
      </div>
    </div>
    <div class="list_grid">
      <div class="list_grid__single">
        <div class="list_grid__single__header fir_header">
          <h2 v-html="$t('partnership.localPartnerHeading')"></h2>
        </div>
        <div class="list_grid__single__content">
          <p>
            {{ $t('partnership.localText1') }} <br/>
            <br/>

            {{ $t('partnership.localText2') }}<br/>
            <br/>

            {{ $t('partnership.localText3') }} <br>
            <br/>

            {{ $t('partnership.localText4') }} <br/>
            <br/>

            {{ $t('partnership.localText5') }} <br/>
            <br/>
          </p>
        </div>
      </div>
      <div class="list_grid__single">
        <div class="list_grid__single__header sec_header">
          <h2 v-html="$t('partnership.cashSosHeading')"></h2>
        </div>
        <div class="list_grid__single__content">
          <h2>{{ $t('partnership.cashSosTitle1') }}</h2>
          <p>
            {{ $t('partnership.cashSosText1') }} <br/>
            {{ $t('partnership.cashSosText2') }} <br/>
            {{ $t('partnership.cashSosText3') }} <br/>
            {{ $t('partnership.cashSosText4') }} <br/>
            {{ $t('partnership.cashSosText5') }} <br/>
            {{ $t('partnership.cashSosText6') }} <br/>
            {{ $t('partnership.cashSosText7') }} <br/>
            {{ $t('partnership.cashSosText8') }} <br/>
            {{ $t('partnership.cashSosText9') }} <br/>
          </p>
          <h2>
            {{ $t('partnership.cashSosTitle2') }}
          </h2>
          <p>
            {{ $t('partnership.cashSosText10') }} <br/>
            {{ $t('partnership.cashSosText11') }} <br/>
            {{ $t('partnership.cashSosText13') }} <br/>
            {{ $t('partnership.cashSosText14') }} <br/>
            {{ $t('partnership.cashSosText15') }} <br/>
            {{ $t('partnership.cashSosText16') }} <br/>
            {{ $t('partnership.cashSosText17') }} <br/>
          </p>
        </div>
      </div>
    </div>
    <h1 class="title">{{ $t('partnership.certificatesHeading') }}</h1>
    <div class="custom_border"/>
    <div class="patents">
      <img src="../assets/img/partnership/pattent1.png"/>
      <img src="../assets/img/partnership/pattent1.png"/>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userScroll: 0,
      footerPos: 0,
      btnStop: false,
      file: []
    };
  },
  methods: {
    getPosition(element) {
      var xPosition = 0;
      var yPosition = 0;

      while (element) {
        xPosition += (element.offsetLeft - element.scrollLeft + element.clientLeft);
        yPosition += (element.offsetTop - element.scrollTop + element.clientTop);
        element = element.offsetParent;
      }
      return yPosition;
    },
  },
  watch: {
    userScroll() {
      this.btnStop = this.userScroll > this.footerPos;
    },
  },
  mounted() {
    window.addEventListener('scroll', e => this.userScroll = window.scrollY);
    var footer = document.getElementById('footer');
    this.footerPos = this.getPosition(footer);
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@import "../assets/style/respond";

.partners {
  position: relative;
  padding-top: 70px;

  &__btn {
    position: fixed;
    bottom: 40px;
    right: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 335px;
    height: 56px;
    text-decoration: none;
    background: #d5dd25;
    box-shadow: 0px 2px 12px rgba(213, 221, 37, 0.25);
    border-radius: 30px;
    @include bold;
    font-size: 18px;
    line-height: 21px;
    text-transform: uppercase;
    color: #623f99;
    cursor: pointer;
    border: none;
    outline: none;
    z-index: 998;

    &--stop {
      position: absolute;
    }

    img {
      margin-left: 13px;
    }
  }

  @include respond(phone) {

    &__btn {
      right: 16px;
      width: 254px;
      font-size: 14px;
      line-height: 17.6px;
    }
  }
}

.partner-welcome {
  padding: 120px 0;
  background-image: url("../assets/img/partnership/partner-bg.png");
  background-repeat: no-repeat;
  background-size: cover;

  &__inner {
    width: 1200px;
    margin: 0 auto;

    p {
      @include normal;
      font-size: 24px;
      line-height: 30px;
      text-align: center;
      color: #FFFFFF;

      &:not(:last-child) {
        margin-bottom: 25px;
      }
    }
  }

  @include respond(tab-land) {
    padding: 120px 30px;

    &__inner {
      width: 738px;
    }
  }

  @include respond(phone) {
    padding: 90px 0;
    background-position: center;

    &__inner {
      width: 343px;

      p {
        font-size: 18px;
        line-height: 22.7px;
      }
    }
  }
}

.terms {
  padding: 120px 0;
  background-color: #F8F2FF;

  @include respond(phone) {
    padding: 40px 0 90px;
  }
}

.title {
  @include bold;
  font-size: 40px;
  line-height: 47px;
  text-align: center;
  text-transform: uppercase;
  color: #623f99;

  @include respond(phone) {
    font-size: 26px;
    line-height: 32.7px;
  }
}

.title + .custom_border {
  @include respond(phone) {
    margin-bottom: 30px;
  }
}

.custom_border {
  width: 160px;
  margin: 7px auto 60px;
  border-bottom: 2px solid #623f99;
}

.title_txt {
  @include normal;
  font-size: 24px;
  line-height: 28px;
  text-align: center;
  color: #131313;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto 36px;

  @include respond(phone) {
    font-size: 14px;
    line-height: 17.6px;
    margin-bottom: 30px;
  }
}

.who_people {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto 20px;

  &:last-of-type {
    margin-bottom: 0;
  }

  &__box {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: #ffffff;
    width: 895px;
    height: 184px;
    box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
    border-radius: 8px;

    .left_side {
      border-radius: 0px 8px 8px 0px !important;
    }

    .vertical_txt {
      width: 82px;
      height: 100%;
      background: #d5dd25;
      border-radius: 8px 0px 0px 8px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;

      p {
        @include bold;
        font-size: 24px;
        line-height: 28px;
        color: #623f99;
        transform: rotate(-90deg);
        width: 155px;
        text-align: center;
      }
    }

    .normal_txt {
      display: flex;
      align-items: center;
      justify-content: space-between;
      width: 100%;
      padding: 0 40px;

      p {
        @include normal;
        font-size: 24px;
        line-height: 28px;
        color: #623f99;

        span {
          @include bold;
        }
      }
    }
  }

  @include respond(tab-land) {
    justify-content: center;
    &__box {
      display: flex;
      width: unset;
      max-width: 375px;
      height: 235px;

      .vertical_txt {
        width: 51px;

        p {
          font-size: 18px;
          line-height: 22px;
        }
      }

      .normal_txt {
        display: flex;
        flex-direction: column-reverse;
        align-items: flex-start;
        padding: 0 20px;

        &--reverse {
          flex-direction: column;
          align-items: flex-end;
        }

        img {
          transform: scale(.9);
          margin-bottom: 20px;
        }

        p {
          font-size: 14px;
          line-height: 17.6px;
        }
      }
    }
  }

  @include respond(phone) {

    &__box {
      width: unset;
      max-width: 343px;
    }
  }
}

.statistics {
  display: flex;
  align-items: center;
  justify-content: center;
  background: #623F99;
  height: 220px;
  width: 100%;

  &__content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 1200px;
    max-width: 100%;

    p {
      @include normal;
      font-size: 16px;
      line-height: 20px;
      text-align: center;
      text-transform: uppercase;
      color: #FFFFFF;

      &:nth-child(2) {
        margin: 20px 0;
      }
    }
  }

  @include respond(tab-land) {
    height: unset;
    padding: 30px 15px;

    &__content {
      flex-direction: column;
      justify-content: center;

      &__txt {
        margin: 40px 0;
      }
    }
  }

  @include respond(phone) {
    &__content {
      p {
        font-size: 14px;
      }
    }
  }
}



.howto {
  padding-top: 80px;
  padding-bottom: 120px;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-image: url("../assets/img/products/click_adv-bg.png");
  background-position-y: -2px;
  background-size: cover;

  h2 {
    @include bold;
    font-size: 24px;
    line-height: 28px;
    text-transform: uppercase;
    color: #623f99;
    margin-bottom: 40px;
  }

  &__step-img {
    margin-top: -30px;
    margin-bottom: 100px;
  }

  @include respond(tab-land) {
    h2 {
      text-align: center;
    }

    &__step-img {
      display: none;
    }
  }

  @include respond(phone) {
    padding-bottom: 90px;

    h2 {
      font-size: 18px;
      line-height: 22.6px;
    }
  }
}

.welcome_img {
  display: none;
  max-width: 100%;
  margin: 0 auto;

  &__mobile-circles {
    display: none;
  }

  &__mobile-step {
    p {
      @include normal;
      margin-top: 15px;
    }
  }

  @include respond(tab-land) {
    display: block;
    width: 767px;
    margin-bottom: 60px;

    &__mobile-circles {
      text-align: center;
      margin: 0 auto;
      display: grid;
      align-items: start;
      justify-content: space-between;
      grid-template-columns: repeat(3, 1fr);
      grid-column-gap: 20px;
      grid-row-gap: 40px;
    }

    &__mobile-step {
      p {
        font-size: 16px;
      }

      &:last-child {
        grid-column: 2 / 3;
      }
    }
  }

  @include respond(phone) {
    width: unset;
    max-width: 375px;

    &__mobile-circles {
      display: block;
    }

    &__mobile-step {

      &:not(:last-child) {
        margin-bottom: 60px;
      }

      p {
        font-size: 14px;
        padding: 0 45px;
      }
    }
  }
}

.model_types {
  display: grid;
  grid-template-columns: repeat(3, 355px);
  justify-content: space-between;
  align-items: stretch;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;

  &__single {
    background: transparent;


    .model_title {
      display: flex;
      justify-content: center;
      align-items: center;
      background: #623f99;
      box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
      height: 58px;

      h2 {
        @include normal;
        font-size: 24px;
        line-height: 28px;
        text-transform: uppercase;
        color: #d5dd25;
        margin-bottom: 0;
      }
    }

    .model_descr {
      box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
      height: 315px;
      background-color: #FFFFFF;
      padding: 30px 20px;
      border-bottom-left-radius: 8px;
      border-bottom-right-radius: 8px;

      p {
        @include normal;
        font-size: 18px;
        line-height: 22px;
        color: #623f99;
        margin-bottom: 5px;

        &:last-of-type {
          margin-bottom: 0;
        }
      }

      .second_box_desc {
        margin-top: 8px;
      }
    }
  }

  @include respond(tab-land) {
    display: flex;
    flex-wrap: wrap;
    align-items: stretch;
    width: 700px;
    justify-content: center;

    &__single {
      width: 373px;

      &:not(:last-child) {
        margin-bottom: 20px;
      }

      .model_title {
        border-radius: 20px 20px 0 0;
      }
    }
  }

  @include respond(phone) {
    width: unset;
    max-width: 400px;
    .model_descr {
      height: unset;

      p {
        @include normal;
        font-size: 14px;
        line-height: 17.6px;
        margin-bottom: 12px;
      }
    }
    &__single {
      width: 343px;
      .model_title {
        h2 {
          font-size: 18px;
          line-height: 22.63px;
        }
      }
    }
  }
}

.first_model_title {
  border-radius: 40px 8px 0px 0px;
}

.second_model_title {
  border-radius: 8px 8px 0px 0px;
}

.third_model_title {
  border-radius: 8px 40px 0px 0px;
}

.download_ques {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 272px;
  background: #623F99;
  padding-top: 60px;
  margin-bottom: 120px;

  p {
    @include normal;
    font-size: 24px;
    line-height: 30px;
    color: #FFFFFF;
    margin-bottom: 36px;
    text-align: center;
  }

  &__btn {
    position: unset !important;
    z-index: 10 !important;
    width: 345px;
  }

  @include respond(phone) {
    height: unset;
    padding-bottom: 60px;
    margin-bottom: 90px;

    p {
      font-size: 14px;
      line-height: 17.6px;
      width: 343px;
    }
  }
}

.costs_txt {
  @include normal;
  font-size: 24px;
  line-height: 30px;
  text-align: center;
  text-transform: uppercase;
  color: #131313;
  margin-bottom: 60px;

  @include respond(phone) {
    width: 343px;
    font-size: 14px;
    line-height: 16.4px;
    margin: 0 auto 30px;
  }
}

.cost_grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;
  padding-bottom: 144px;

  &__single {
    width: 387px;
    height: 277px;
    background: #ffffff;
    box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
    border-radius: 8px;
    text-align: center;
    padding-top: 60px;

    &:not(last-child) {
      margin-right: 18px;
      margin-bottom: 20px;
    }

    &:nth-child(3) {
      margin-right: 0;
    }

    p {
      @include normal;
      font-size: 16px;
      line-height: 20px;
      text-align: center;
      text-transform: uppercase;
      color: #131313;
      margin-top: 30px;
    }
  }

  @include respond(tab-land) {
    width: 767px;

    &__single {
      width: 373px;

      &:not(last-child) {
        margin-right: 18px;
        margin-bottom: 20px;
      }

      &:nth-child(2), &:nth-child(4){
        margin-right: 0;
      }

      &:nth-child(3) {
        margin-right: 18px;
      }
    }
  }

  @include respond(phone) {
    width: unset;
    max-width: 375px;

    &__single {
      width: 343px;
      height: unset;
      text-align: center;
      padding: 30px 0;

      margin-right: 0 !important;

      p {
        @include normal;
        font-size: 14px;
        line-height: 17.6px;
        margin-top: 20px;
      }
    }
  }
}

.list_grid {
  display: grid;
  grid-template-columns: repeat(2, 590px);
  justify-content: space-between;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;
  padding-bottom: 120px;

  &__single {
    &__header {
      height: 58px;
      padding-top: 15px;

      h2 {
        @include normal;
        font-size: 24px;
        line-height: 28px;
        text-align: center;
        text-transform: uppercase;
      }
    }

    &__content {
      padding: 30px 40px;
      background: #ffffff;
      height: 729px;
      box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);

      p {
        @include normal;
        font-size: 16px;
        line-height: 19px;
        color: #131313;
      }

      h2 {
        //@include medium;
        font-size: 16px;
        line-height: 19px;
        text-transform: uppercase;
        color: #623f99;
        margin-bottom: 10px;

        &:last-of-type {
          margin-top: 30px;
        }
      }
    }
  }

  @include respond(tab-land) {
    grid-template-columns: repeat(1, 1fr);
    grid-gap: 20px;
    width: 767px;

    &__single {
      &__content {
        height: unset;
        border-radius: 0 0 8px 8px;
      }
    }
  }

  @include respond(phone) {
    width: unset;
    max-width: 343px;
    padding-bottom: 90px;

    &__single {
      &__header {
        height: unset;
        padding: 20px 0;

        h2 {
          font-size: 18px;
          line-height: 22.6px;
        }
      }

      &__content {
        padding: 30px 20px;

        p {
          font-size: 14px;
          line-height: 17.6px;
        }

        h2 {
          font-size: 14px;
          line-height: 17.6px;

          &:last-of-type {
            margin-top: 20px;
          }
        }
      }
    }
  }
}

.fir_header {
  background: #d5dd25;
  box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
  border-radius: 40px 8px 0px 0px;

  h2 {
    color: #623f99;
  }

  @include respond(tab-land) {
    border-radius: 20px 20px 0 0;
  }
}

.sec_header {
  background: #623f99;
  box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
  border-radius: 8px 40px 0px 0px;

  h2 {
    color: #d5dd25;
  }

  @include respond(tab-land) {
    border-radius: 20px 20px 0 0;
  }
}

.patents {
  display: flex;
  align-items: center;
  justify-content: center;
  padding-bottom: 120px;

  img {
    margin: 0 20px;
  }

  @include respond(phone) {
    flex-wrap: wrap;
    flex-direction: column;

    img {
      margin: 0;

      &:first-child {
        margin-bottom: 20px;
      }
    }
  }
}
</style>

<style>
.statistics .statistics__content p span {
  color: #d5dd25;
  font-weight: 700;
}

.model_types .model_title h2 span {
  font-weight: 700;
}

.costs_txt span {
  color: #623f99;
}

.list_grid .list_grid__single .list_grid__single__header h2 span {
  font-weight: 700;
}
</style>
