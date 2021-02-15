<template>
  <div class="representations">
    <h3 class="representations__title">
      {{ $t('branchesTitle') }}
    </h3>

    <div class="representations__map">
      <div class="representations__map-box">
        <div v-for="count in countries">
          <img :src="count.country_position_on_map"
               alt=""
               v-if="country === count.eng_lang_country">

          <div class="representations__info-box info-box" v-if="country === count.eng_lang_country">
            <div class="info-box__title">
              <span v-if="$i18n.locale === 'ru'">{{ count.rus_lang_country }}</span>
              <span v-else>{{ count.eng_lang_country }}</span>
            </div>
            <div class="info-box__list"
                 v-if="(count.rus_lang_terminal_or_mobile !== null || count.eng_lang_terminal_or_mobile !== null) && count.workers !== null && count.clients !== null">
              <div class="info-box__item">
                <img src="../assets/img/agencies/location-pin.svg" alt="">
                <span v-if="$i18n.locale === 'ru'">{{ count.rus_lang_terminal_or_mobile }}</span>
                <span v-else>{{ count.eng_lang_terminal_or_mobile }}</span>
              </div>
              <div class="info-box__item">
                <img src="../assets/img/agencies/user.svg" alt="">
                <span v-if="$i18n.locale === 'ru'">{{ count.workers }} работников</span>
                <span v-else>{{ count.workers }} employees</span>
              </div>
              <div class="info-box__item">
                <img src="../assets/img/agencies/briefcase.svg" alt="">
                <span v-if="$i18n.locale === 'ru'">{{ count.clients }} клиентов</span>
                <span v-else>{{ count.clients }} clients</span>
              </div>
            </div>
            <div class="info-box__target" v-else>
              <img src="../assets/img/agencies/target.svg" alt="">
              <span v-if="$i18n.locale === 'ru'">Таргет 2021</span>
              <span v-else>Target 2021</span>
            </div>
          </div>

        </div>

        <div class="representations__countries">
          <img :src="c.country_flag"
               id="clicked-flag"
               v-for="c in countries"
               alt=""
               @click="chooseCountry(c.eng_lang_country)"
               :class="country === c.eng_lang_country ? 'active' : ''">
        </div>
      </div>

      <div class="swiper-container representations__mobile-box">
        <div class="swiper-wrapper">
          <div v-for="(count, i) in countries" class="swiper-slide">
            <div class="representations__img-box">
              <img :src="count.country_map"
                   alt="">
            </div>

            <div class="representations__info-box info-box">
              <div class="info-box__title">
                <span v-if="$i18n.locale === 'ru'">{{ count.rus_lang_country }}</span>
                <span v-else>{{ count.eng_lang_country }}</span>
              </div>
              <div class="info-box__list"
                   v-if="(count.rus_lang_terminal_or_mobile !== null || count.eng_lang_terminal_or_mobile !== null) && count.workers !== null && count.clients !== null">
                <div class="info-box__item">
                  <img src="../assets/img/agencies/location-pin.svg" alt="">
                  <span v-if="$i18n.locale === 'ru'">{{ count.rus_lang_terminal_or_mobile }}</span>
                  <span v-else>{{ count.eng_lang_terminal_or_mobile }}</span>
                </div>
                <div class="info-box__item">
                  <img src="../assets/img/agencies/user.svg" alt="">
                  <span v-if="$i18n.locale === 'ru'">{{ count.workers }} работников</span>
                  <span v-else>{{ count.workers }} employees</span>
                </div>
                <div class="info-box__item">
                  <img src="../assets/img/agencies/briefcase.svg" alt="">
                  <span v-if="$i18n.locale === 'ru'">{{ count.clients }} клиентов</span>
                  <span v-else>{{ count.clients }} clients</span>
                </div>
              </div>
              <div class="info-box__target" v-else>
                <img src="../assets/img/agencies/target.svg" alt="">
                <span v-if="$i18n.locale === 'ru'">Таргет 2021</span>
                <span v-else>Target 2021</span>
              </div>
            </div>

            <div class="representations__count-box">
              <span>{{i + 1}}</span> / {{ countries.length }}
            </div>
          </div>
        </div>
        <!-- Add Arrows -->
        <div class="swiper-button-next"></div>
        <div class="swiper-button-prev"></div>
      </div>
    </div>
  </div>
</template>

<script>
import Swiper, {Navigation} from 'swiper';

Swiper.use([Navigation]);

let timer = null;
const AUTO_INTERVAL = 4000;

export default {
  data() {
    return {
      country: "Kazakhstan",
      countries: [],
      playing: false,
      currentIndex: 0
    };
  },
  methods: {
    chooseCountry(str) {
      this.country = str;
      clearInterval(timer);
      this.setAutoRoll();
    },
    setAutoRoll() {
      let vueSelf = this;
      timer = setInterval(function () {
        vueSelf.addIndex();
      }, AUTO_INTERVAL);
    },
    addIndex() {
      let newIndex = this.currentIndex + 1;
      this.currentIndex = newIndex === this.countries.length ? 0 : newIndex;
    },
    play() {
      this.setAutoRoll();
      this.playing = true;
    },
  },
  watch: {
    currentIndex() {
      let clickedFlag = this.countries[this.currentIndex].eng_lang_country;
      this.chooseCountry(clickedFlag);
    }
  },

  mounted() {
    this.$axios.get("http://185.100.65.231/api/country-list/")
      .then(response => (this.countries = response.data));
    if(window.innerWidth > 767) {
      this.play();
    }
  },

  updated() {
    var swiper = new Swiper('.representations__mobile-box', {
      slidesPerView: 1,
      spaceBetween: 60,
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
    });
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@import "../assets/style/respond";
@import '../node_modules/swiper/swiper-bundle.css';

//representations
.representations {
  text-align: center;
  //padding-top: 120px;
  &__title {
    display: inline-block;
    @include bold;
    font-size: 40px;
    text-transform: uppercase;
    color: #623f99;
    position: relative;
    margin-bottom: 8px;

    &:after {
      content: '';
      width: 160px;
      height: 2px;
      background-color: #623f99;
      position: absolute;
      top: calc(100% + 7px);
      left: 50%;
      transform: translateX(-50%);
    }
  }

  &__map {
    max-width: 1200px;
    margin: 0 auto;
    position: relative;

    img {

    }
  }

  &__countries {

    img {
      cursor: pointer;
      width: 25px;
      height: 25px;
      border-radius: 50%;

      &:not(:last-child) {
        margin-right: 30px;
      }

      &.active {
        filter: drop-shadow(0px 0px 10px rgba(98, 63, 153, 0.5));
      }
    }
  }

  &__info-box {

  }

  &__mobile-box {
    display: none;
  }

  &__img-box {
    position: relative;
    width: 375px;
    height: 260px;
    overflow: hidden;

    img {
      width: 100%;
      position: absolute;
      right: 0;
      top: 0;
      transform: translateY(-10%);
    }
  }

  &__count-box {
    position: absolute;
    bottom: -48px;
    left: 50%;
    transform: translateX(-50%);

    @include normal;
    font-size: 18px;
    color: #b9b9b9;

    span {
      font-weight: 700;
      color: #623F99;
    }
  }

  @include respond(phone) {

    &__map {
      max-width: 375px;
      margin-top: 26px;
    }

    &__title {
      font-size: 26px;
    }

    &__map-box {
      display: none;
    }

    &__mobile-box {
      display: block;
      padding-bottom: 72px;
    }
  }
}

.info-box {
  position: absolute;
  min-height: 90px;
  bottom: 60px;
  left: 50px;
  background-color: #FFFFFF;
  box-shadow: 0 4px 20px rgba(146, 115, 194, 0.5);
  border-radius: 8px;

  padding: 12px;

  text-align: left;

  &__title {
    @include bold;
    font-size: 16px;
    line-height: 20px;
    color: #623F99;
    text-transform: uppercase;

    margin-bottom: 7px;
  }

  &__item {
    display: flex;
    align-items: center;

    @include normal;
    font-size: 16px;
    line-height: 20px;
    color: #131313;

    img {
      margin-right: 6px;
    }

    &:not(:last-child) {
      margin-bottom: 3px;
    }
  }

  &__target {
    display: flex;
    align-items: center;

    @include normal;
    font-size: 16px;
    line-height: 20px;
    color: #131313;

    img {
      margin-right: 6px;
    }
  }

  @include respond(tab-land) {
    bottom: 10px;
    left: 10px;
    padding: 5px;
    width: 185px;
  }
}

.swiper-button-prev, .swiper-container-rtl .swiper-button-next,
.swiper-button-next, .swiper-container-rtl .swiper-button-prev {
  bottom: 20px;
  top: unset;
}

.swiper-button-prev, .swiper-container-rtl .swiper-button-next {
  left: 110px;
}
.swiper-button-next, .swiper-container-rtl .swiper-button-prev {
  right: 110px;
}

.swiper-button-prev:after, .swiper-button-next:after {
  color: #D5DD25;
  font-size: 32px;
}
</style>
