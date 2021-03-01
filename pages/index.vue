<template>
  <div class="index">
    <div class="welcome">
      <div class="welcome__content">
        <h1 v-html="$t('home.welcomeTitle')"></h1>
        <div class="custom_border"/>
        <p>{{ $t('home.welcomeSubtitle') }}</p>
        <button v-scroll-to="{el:'#footer', duration: 700,}">{{ $t('contactBtn') }}</button>
      </div>
    </div>
    <div class="sponsors">
      <div class="sponsors__wrapper">
        <img src="../assets/img/main/bottomLogo1.png"/>
        <img src="../assets/img/main/bottomLogo2.png"/>
        <img src="../assets/img/main/bottomLogo3.png"/>
        <img src="../assets/img/main/bottomLogo4.png"/>
      </div>
    </div>
    <div class="about">
      <div class="fixed__bg"/>
      <div class="about__content">
        <h1>{{ $t('home.aboutUs') }}</h1>
        <p v-html="$t('home.aboutText1')"></p>
        <p v-html="$t('home.aboutText2')"></p>
        <p v-html="$t('home.aboutText3')"></p>
        <p v-html="$t('home.aboutText4')"></p>
      </div>
    </div>
    <div class="products">
      <h1>{{ $t('home.ourProducts') }}</h1>
      <div class="cus_bord"/>
      <div class="products__grid">
        <nuxt-link
          tag="div"
          to="/Products"
          class="products__grid__single"
        >
          <div>
            <h2>DoZP.kz</h2>
            <div class="grid_bord"/>
            <p v-html="$t('home.dozpText')"></p>
          </div>
          <img src="../assets/img/main/pr1.png" alt="">
        </nuxt-link>
        <nuxt-link
          tag="div"
          to="/Products"
          class="products__grid__single"
        >
          <div>
            <h2>{{ $t('home.terminal') }}</h2>
            <div class="grid_bord"/>
            <p v-html="$t('home.terminalText')"></p>
          </div>
          <img src="../assets/img/main/pr2.png" alt="">
        </nuxt-link>
        <nuxt-link
          tag="div"
          to="/Products"
          class="products__grid__single"
        >
          <div>
            <h2>Click Advance</h2>
            <div class="grid_bord"/>
            <p v-html="$t('home.clickAdvanceText')"></p>
          </div>
          <img src="../assets/img/main/pr3.png" alt="">
        </nuxt-link>
      </div>
    </div>

    <div class="feature">
      <p class="feature__text" v-html="$t('home.featureText')"></p>

      <h4 class="feature__title" v-html="$t('home.featureTitle')"></h4>

      <div class="feature__items">
        <p class="feature__item" v-html="$t('home.featureItem1')"></p>
        <p class="feature__item" v-html="$t('home.featureItem2')"></p>
        <p class="feature__item" v-html="$t('home.featureItem3')"></p>
      </div>
    </div>

    <div class="main-features">
      <h3 class="main-features__title" v-html="$t('home.mainFeaturesTitle')"></h3>

      <div class="main-features__row">
        <div class="main-features__box">
          <img src="../assets/img/main/cash.png" alt="">
          <h5>
            {{ $t('home.featureItemTitle1') }}
          </h5>
          <p>
            {{ $t('home.featureItemText1') }}
          </p>
        </div>
        <div class="main-features__box">
          <img src="../assets/img/main/investment.png" alt="">
          <h5>
            {{ $t('home.featureItemTitle2') }}
          </h5>
          <p>
            {{ $t('home.featureItemText2') }}
          </p>
        </div>
        <div class="main-features__box">
          <img src="../assets/img/main/online-learning.png" alt="">
          <h5>
            {{ $t('home.featureItemTitle3') }}
          </h5>
          <p>
            {{ $t('home.featureItemText3') }}
          </p>
        </div>
      </div>
    </div>

    <div class="support_txt">
      <h1>{{ $t('home.missionTitle') }}</h1>
      <div class="support_txt__bord"/>
      <p class="support_txt__subtitle" v-html="$t('home.missionSubtitle')"></p>
      <div class="advantages_wrapper">
        <div class="advantages">
          <div class="advantages__single">
            <div class="img_title">
              <img src="../assets/img/main/111.png"/>
              <h2>{{ $t('home.missionTitle1') }}</h2>
            </div>
            <p>{{ $t('home.missionText1') }}</p>
          </div>
          <div class="advantages__single">
            <div class="img_title">
              <img src="../assets/img/main/222.png"/>
              <h2>{{ $t('home.missionTitle2') }}</h2>
            </div>
            <p>{{ $t('home.missionText2') }}</p>
          </div>
          <div class="advantages__single">
            <div class="img_title">
              <img src="../assets/img/main/333.png"/>
              <h2>
                {{ $t('home.missionTitle3') }}
              </h2>
            </div>
            <p>{{ $t('home.missionText3') }}</p>
          </div>
          <div class="advantages__single">
            <div class="img_title">
              <img src="../assets/img/main/444.png"/>
              <h2>{{ $t('home.missionTitle4') }}</h2>
            </div>
            <p>{{ $t('home.missionText4') }}</p>
          </div>
        </div>
      </div>
    </div>

    <representations-map class="branches"></representations-map>

    <div class="articles">
      <h1>{{ $t('newsTitle') }}</h1>
      <div class="articles_bord"/>
      <div class="articles__container">

        <div class="swiper-container">
          <div class="swiper-wrapper">
            <div class="swiper-slide single_item" v-for="n in news">
              <img :src="n.img"/>
              <p class="single_item__date">{{ n.created_date | moment("YYYY - MM - DD") }}</p>
              <h2 class="single_item__title" v-if="$i18n.locale === 'ru'" @click="openModal(n)">{{ n.rus_lang_title }}</h2>
              <h2 class="single_item__title" v-else @click="openModal(n)">{{ n.eng_lang_title }}</h2>
              <p class="single_item__descr" v-if="$i18n.locale ==='ru'">{{ n.rus_lang_short_text }}</p>
              <p class="single_item__descr" v-else>{{ n.eng_lang_short_text }}</p>
              <p class="single_item__more" @click="openModal(n)">
                {{ $t('home.readMore') }}
              </p>
            </div>
          </div>
          <!-- Add Arrows -->
          <div class="swiper-button-next"></div>
          <div class="swiper-button-prev"></div>
        </div>

      </div>
    </div>

    <news-modal v-if="showModal" :newsContent=curModalContent @close="showModal = false">
      <h3 slot="header">custom header</h3>
    </news-modal>
  </div>
</template>

<script>
import NewsModal from "@/components/NewsModal";
import RepresentationsMap from "@/components/RepresentationsMap";
import Swiper, {Navigation} from 'swiper';

Swiper.use([Navigation]);

export default {
  components: {
    NewsModal,
    RepresentationsMap,
  },
  data() {
    return {
      showModal: false,
      news: [],
      curModalContent: null,
    };
  },
  methods: {
    openModal(n) {
      this.showModal = true;
      this.curModalContent = n;
    },
  },
  mounted() {
    this.$axios.get("https://cashsoswiftly.com/api/news-list/")
      .then(response => (this.news = response.data));
  },
  updated() {
    var swiper = new Swiper('.swiper-container', {
      slidesPerView: 1,
      spaceBetween: 60,
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
      breakpoints: {
        768: {
          slidesPerView: 2,
          spaceBetween: 30,
        },
        1200: {
          slidesPerView: 3,
          spaceBetween: 26
        }
      }
    });
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@import "../assets/style/respond";
@import '../node_modules/swiper/swiper-bundle.css';

.index {
  padding-top: 70px;
  overflow: hidden;
}

// welcome
.welcome {
  position: relative;
  background-image: url("../assets/img/main/bg.png");
  background-size: cover;
  background-repeat: no-repeat;
  padding-top: 173px;
  height: 610px;
  //width: 100%;

  &__content {
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;

    h1 {
      @include bold;
      font-size: 60px;
      line-height: 70px;
      color: #ffffff;
      text-shadow: 0px 0px 4px rgba(0, 0, 0, 0.5);
    }

    .custom_border {
      margin-top: 10px;
      margin-bottom: 20px;
      width: 200px;
      border: 2px solid #d5dd25;
    }

    p {
      @include normal;
      font-size: 24px;
      line-height: 28px;
      color: #ffffff;
      text-shadow: 0px 0px 4px rgba(0, 0, 0, 0.5);
      margin-bottom: 50px;
    }

    button {
      //@include medium;
      font-size: 18px;
      @include bold;
      //line-height: 21px;
      text-transform: uppercase;
      color: #623f99;
      background: #d5dd25;
      box-shadow: 0px 2px 12px rgba(213, 221, 37, 0.25);
      border-radius: 30px;
      width: 296px;
      height: 56px;
      border: none;
      outline: none;
      cursor: pointer;
    }

    @include respond(tab-land) {
      width: 767px;
    }

    @include respond(phone) {
      max-width: 375px;
      width: unset;
      padding-left: 15px;
      padding-right: 15px;

      h1 {
        font-size: 32px;
        line-height: 40px;
      }

      p {
        font-size: 18px;
        line-height: 23px;
      }
    }
  }
}

// sponsors
.sponsors {
  background: #f8f2ff;

  &__wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 20px 0;
    flex-wrap: wrap;
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;

    @include respond(tab-land) {
      width: 767px;
    }

    @include respond(phone) {
      max-width: 375px;
      padding-left: 15px;
      padding-right: 15px;
      justify-content: unset;
      gap: 25px;

      img {
        &:nth-child(1) {
          width: 133px;
          height: 27px;
          margin-right: 50px;
          margin-left: 20px;
        }

        &:nth-child(2) {
          width: 75px;
          height: 44px;
        }

        &:nth-child(3) {
          width: 41px;
          height: 49px;
          margin-right: 75px;
          margin-left: 60px;
        }

        &:nth-child(4) {
          width: 112px;
          height: 45px;
        }
      }
    }
  }
}

// about
.about {
  position: relative;
  height: 534px;
  margin: 120px 0;

  //overflow: hidden;
  .fixed__bg {
    position: absolute;
    top: 0;
    left: 0;
    height: 534px;
    width: calc(100vw - 455px);
    background-color: rgba(246, 239, 255, 0.8);
    z-index: -1;

    @include respond(tab-land) {
      width: 100%;
      height: 100%;
    }
  }

  &__content {
    position: relative;
    width: 1200px;
    height: 100%;
    max-width: 100%;
    margin: 0 auto;
    padding-top: 40px;
    padding-left: 39px;

    @include respond(tab-land) {
      width: 767px;
      padding: 93px 0 60px;
      text-align: center;
      position: unset;
    }

    h1 {
      @include bold;
      font-size: 40px;
      line-height: 47px;
      text-transform: uppercase;
      color: #623f99;
      padding-bottom: 10px;
      border-bottom: 2px solid #623f99;
      margin-bottom: 32px;
      display: inline-block;
    }

    p {
      position: relative;
      @include normal;
      font-size: 18px;
      line-height: 21px;
      color: #131313;
      margin-bottom: 35px;
      max-width: 583px;
      text-align: left;

      &::after {
        content: url("../assets/img/main/checkbox.png");
        position: absolute;
        top: 2px;
        left: -39px;
      }

      &:last-of-type {
        margin-bottom: 0;
      }

      @include respond(tab-land) {
        padding-left: 35px;

        &:after {
          left: 0;
        }
      }
    }

    &::before {
      content: url("../assets/img/main/about.png");
      position: absolute;
      right: -100px;
      top: 120px;

      @include respond(tab-land) {
        right: unset;
        left: 50%;
        transform: translateX(-50%) scale(0.7);
        top: -320px;
      }
    }
  }

  @include respond(tab-land) {
    height: unset;
    margin-top: 350px;
  }

  @include respond(phone) {
    margin-top: 250px;
    margin-bottom: 90px;

    &__content {
      width: unset;
      max-width: 375px;
      padding-left: 15px;
      padding-right: 15px;

      &::before {
        transform: translateX(-50%) scale(0.5);
      }

      h1 {
        font-size: 26px;
        line-height: 32px;
      }
    }
  }
}

// products
.products {
  padding-bottom: 120px;

  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-align: center;
    text-transform: uppercase;
    color: #623f99;
  }

  .cus_bord {
    width: 160px;
    border-bottom: 2px solid #623f99;
    margin: 10px auto 60px;
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(3, 387px);
    justify-content: space-between;
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;

    @include respond(tab-land) {
      width: 767px;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }

    //.grid_first {
    //  background-image: url("../assets/img/main/pr1.png");
    //}
    //
    //.grid_second {
    //  background-image: url("../assets/img/main/pr2.png");
    //  background-repeat: no-repeat;
    //}
    //
    //.grid_third {
    //  background-image: url("../assets/img/main/pr3.png");
    //}

    &__single {
      background: #ffffff;
      box-shadow: 0px 4px 12px rgba(146, 115, 194, 0.5);
      text-align: right;
      cursor: pointer;
      display: flex;
      align-items: center;
      padding: 30px 30px 30px 40px;

      @include respond(tab-land) {
        width: 373.5px;
        height: 371px;

        &:not(:last-child) {
          margin-bottom: 20px;
        }

        &:first-child {
          margin-right: 20px;
        }
      }

      @include respond(phone) {
        width: 343px;
        margin-right: 0;

        &:first-child {
          margin-right: 0;
        }
      }

      img {
        margin-left: 30px;
      }

      &:nth-child(2) {
        img {
          margin-left: 0;
        }
      }

      h2 {
        //@include medium;
        font-size: 24px;
        line-height: 28px;
        text-transform: uppercase;
        color: #623f99;
      }

      .grid_bord {
        width: 60px;
        border-bottom: 1px solid #623f99;
        margin-top: 10px;
        margin-bottom: 20px;
        margin-left: auto;
      }

      p {
        @include normal;
        font-size: 16px;
        line-height: 19px;
        color: #131313;
      }
    }
  }

  @include respond(phone) {
    h1 {
      font-size: 26px;
      line-height: 32px;
    }
    .cus_bord {
      margin-bottom: 45px;
    }
  }
}

// features
.feature {
  background-image: url("../assets/img/main/feature-bg.png");
  background-repeat: no-repeat;
  background-size: cover;
  padding: 120px 0 88px;

  &__text {
    @include light;
    font-size: 18px;
    color: #ffffff;
    text-align: center;
    margin-bottom: 25px;
  }

  &__title {
    @include normal;
    font-size: 24px;
    line-height: 30px;
    color: #d5dd25;
    text-align: center;
    margin-bottom: 90px;
  }

  &__items {
    width: 63.4%;
    padding: 70px 0 70px 142px;
    background-color: #E2E787;
    margin-left: auto;
    position: relative;

    &:after {
      content: '';
      background-image: url("../assets/img/main/feature-img.png");
      width: 472px;
      height: 352px;
      position: absolute;
      top: 36px;
      right: 92.88%;
    }
  }

  &__item {
    position: relative;
    @include normal;
    font-size: 18px;
    line-height: 22px;
    color: #131313;

    &:not(:last-child) {
      margin-bottom: 30px;
    }

    &:before {
      content: '';
      background-image: url("../assets/img/main/purple-checkbox.png");
      width: 25px;
      height: 17px;
      position: absolute;
      top: 0;
      left: -32px;
    }
  }

  @include respond(tab-land) {
    padding-bottom: 0;

    &__text {
      max-width: 767px;
      margin-left: auto;
      margin-right: auto;
    }

    &__title {
      max-width: 767px;
      margin-left: auto;
      margin-right: auto;
      margin-bottom: 240px;
    }

    &__items {
      width: unset;
      background-color: #E2E787;
      margin-left: unset;

      &:after {
        width: 472px;
        height: 352px;
        top: -260px;
        right: 50%;
        transform: translateX(50%) scale(0.7);
      }
    }
  }

  @include respond(phone) {
    &__text {
      max-width: 375px;
      padding-left: 15px;
      padding-right: 15px;
    }

    &__title {
      max-width: 375px;
      padding-left: 15px;
      padding-right: 15px;
    }

    &__items {
      padding-left: 40px;
      padding-right: 15px;
    }

    &__item {
      &:before {
        background-image: url("../assets/img/main/purple-checkbox-sm.png");
        width: 14px;
        height: 14px;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        top: 3px;
        left: -20px;
      }
    }
  }
}

//main-features
.main-features {
  padding: 120px 0;
  background-color: #D0C5E0;

  &__title {
    @include bold;
    font-size: 24px;
    color: #623F99;
    line-height: 30px;
    text-align: center;
    text-transform: uppercase;
    margin-bottom: 40px;
  }

  &__row {
    display: flex;
    flex-wrap: wrap;
    width: 1200px;
    margin: 0 auto;
    //align-items: flex-start;
  }

  &__box {
    padding: 30px 20px;
    background: #FFFFFF;
    box-shadow: 0 4px 20px rgba(146, 115, 194, 0.5);
    border-radius: 8px;
    width: 386px;

    &:not(:last-child) {
      margin-right: 20px;
    }

    img {
      display: block;
      margin: 0 auto 20px;
    }

    h5 {
      @include bold;
      font-size: 24px;
      line-height: 30px;
      color: #623f99;
      text-transform: uppercase;
      margin-bottom: 20px;
    }

    p {
      @include normal;
      font-size: 16px;
      line-height: 20px;
      color: #131313;
    }
  }

  @include respond(tab-land) {
    &__row {
      width: 767px;
      justify-content: center;
    }

    &__box {
      width: 372px;

      &:not(:last-child) {
        margin-right: 0;
        margin-bottom: 20px;
      }

      &:first-child {
        margin-right: 20px;
      }
    }
  }

  @include respond(phone) {
    padding: 60px 0;

    &__title {
      padding: 0 15px;
      font-size: 18px;
    }

    &__row {
      max-width: 375px;
    }

    &__box {
      width: 343px;

      &:first-child {
        margin-right: 0;
      }

      h5 {
        font-size: 18px;
        line-height: 22.63px;
        margin-bottom: 10px;
      }
    }
  }
}

// sup txt
.support_txt {
  background-image: url("../assets/img/main/suptxt.png");
  background-size: 100% 100%;
  padding-top: 60px;
  padding-bottom: 120px;
  //height: 291px;

  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-align: center;
    text-transform: uppercase;
    color: #d5dd25;
  }

  &__bord {
    width: 160px;
    margin: 10px auto 30px;
    border-bottom: 2px solid #d5dd25;
  }

  &__subtitle {
    @include light;
    font-size: 24px;
    line-height: 28px;
    color: #ffffff;
    max-width: 1200px;
    text-align: center;
    margin: 0 auto 57px;

    span {
      color: #d5dd25;
      font-weight: 700;
    }

    @include respond(tab-land) {
      width: 767px;
    }
  }

  @include respond(phone) {
    background-image: linear-gradient(0deg, rgba(63, 46, 89, 0.9), rgba(63, 46, 89, 0.9));

    h1 {
      font-size: 26px;
      line-height: 32px;
    }

    &__bord {
      width: 68px;
    }

    &__subtitle {
      width: 375px;
      font-size: 14px;
      line-height: 17.5px;
      margin-bottom: 40px;
    }
  }
}

// advantages
.advantages_wrapper {

}

.advantages {
  display: grid;
  grid-template-columns: repeat(2, 590px);
  grid-row-gap: 20px;
  justify-content: space-between;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;

  &__single {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    background: #ffffff;
    box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
    border-radius: 8px;
    padding: 30px 20px 25px 15px;

    .img_title {
      text-align: center;
      width: 284px;
      flex-shrink: 0;

      img {
        margin-bottom: 30px;
      }

      h2 {
        @include bold;
        font-size: 24px;
        line-height: 30px;
        text-align: center;
        text-transform: uppercase;
        color: #623f99;
      }
    }

    p {
      @include normal;
      font-size: 16px;
      line-height: 19px;
      color: #131313;
      max-width: 265px;
      margin-left: 35px;
    }

    @include respond(tab-land) {
      flex-direction: column;
      padding: 25px 15px;
      justify-content: center;

      .img_title {
        width: unset;
        height: 174px;
        margin-bottom: 20px;
      }

      p {
        margin: 0;
        max-width: unset;
      }
    }
  }

  @include respond(tab-land) {
    grid-template-columns: repeat(2, 373px);
    grid-gap: 20px;
    width: 767px;
  }

  @include respond(phone) {
    grid-template-columns: repeat(1, 343px);
    max-width: 375px;
    justify-content: center;

    .img_title {

      height: unset;
      margin-bottom: 10px;
      h2 {
        font-size: 18px;
        line-height: 22.6px;
      }
    }
  }
}

.branches {
  margin-top: 120px;

  @include respond(phone) {
    margin-top: 90px;
  }
}

// articles
.articles {
  padding: 120px 0;

  &__container {
    width: 1200px;
    margin: 0 auto;

    @include respond(tab-land) {
      width: 767px;
    }
  }

  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-align: center;
    text-transform: uppercase;
    color: #623f99;
  }

  .articles_bord {
    margin: 10px auto 60px;
    width: 160px;
    border-bottom: 2px solid #623f99;
  }

  @include respond(tab-land) {

  }

  @include respond(phone) {
    padding: 90px 0;

    &__container {
      max-width: 375px;
      width: unset;
    }

    h1 {
      //@include medium;
      font-size: 26px;
      line-height: 32px;
    }

    .articles_bord {
      margin: 5px auto 40px;
      width: 68px;
    }
  }
}

.single_item {
  width: 370px;

  img {
    width: 387px;
    height: 274px;
  }

  &__date {
    @include normal;
    font-size: 16px;
    line-height: 19px;
    color: #acacac;
    margin-top: 10px;
    margin-bottom: 20px;
  }

  &__title {
    @include bold;
    font-size: 24px;
    line-height: 28px;
    margin-bottom: 10px;
    color: #623f99;
    cursor: pointer;
  }

  &__descr {
    @include normal;
    font-size: 16px;
    line-height: 20px;
    color: rgba(19, 19, 19, 0.8);
  }

  &__more {
    display: inline-block;
    position: relative;
    @include normal;
    font-size: 16px;
    line-height: 19px;
    text-transform: uppercase;
    color: rgba(19, 19, 19, 0.5);
    margin-top: 30px;
    cursor: pointer;

    &::before {
      content: url("../assets/img/main/go.png");
      position: absolute;
      right: -26px;
      top: -2px;
    }
  }

  @include respond(tab-land) {
    width: 340.5px;
  }

  @include respond(phone) {
    max-width: 255px;
    margin: 0 auto;

    img {
      width: 255px;
      height: 180px;
    }

    &__date {
      font-size: 14px;
      line-height: 17.6px;
    }

    &__title {
      font-size: 18px;
      line-height: 22.6px;
    }

    &__descr {
      font-size: 14px;
      line-height: 17.6px;
    }

    &__more {
      font-size: 14px;
      line-height: 17.6px;

      &::before {
        content: url("../assets/img/main/go.png");
        position: absolute;
        right: -26px;
        top: -2px;
      }
    }
  }
}

.swiper-container {
  padding: 0 25px;

  @include respond(tab-land) {
    padding: 0 28px;
  }

  @include respond(phone) {
    padding: 0 60px;
  }
}
.swiper-button-prev, .swiper-container-rtl .swiper-button-next {
  left: 1px;

  @include respond(phone) {
    left: 20px;
  }
}
.swiper-button-next, .swiper-container-rtl .swiper-button-prev {
  right: 1px;

  @include respond(phone) {
    right: 20px;
  }
}

.swiper-button-prev:after, .swiper-button-next:after{
  font-size: 30px !important;
  color: #e8e8e8;

  @include respond(phone) {
    font-size: 40px !important;
  }
}

</style>

<style lang="scss">

body {
  overflow-x: hidden;
}

img {
  max-width: 100%;
  width: auto;
}

.about .about__content p span {
  font-weight: 700;
  color: #623F99;
}

.feature .feature__text span {
  color: #d5dd25;
  font-weight: 700;
}

.support_txt .support_txt__subtitle span {
  color: #d5dd25;
  font-weight: 700;
}
</style>
