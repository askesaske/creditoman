<template>
  <div class="solo">
    <div class="header_descr">
      <div class="country-row">
        <div class="country_menu">
          <h1 v-if="$i18n.locale === 'ru'">{{ country.rus_lang_country }}</h1>
          <h1 v-else>{{ country.eng_lang_country }}</h1>
          <div class="country_menu__items">
            <div class="country_menu__item">
              <p>{{ $t('branch.population') }}</p>
              <p v-if="$i18n.locale === 'ru'">{{ country.rus_lang_population }}</p>
              <p v-else>{{ country.eng_lang_population }}</p>
            </div>
            <div class="country_menu__item">
              <p>{{ $t('branch.gpd') }}</p>
              <p v-if="$i18n.locale === 'ru'">{{ country.rus_lang_gdp }}</p>
              <p v-else>{{ country.eng_lang_gdp }}</p>
            </div>
            <div class="country_menu__item">
              <p>{{ $t('branch.mainIndustries') }}</p>
              <p v-if="$i18n.locale === 'ru'">{{ country.rus_lang_main_industries }}</p>
              <p v-else>{{ country.eng_lang_main_industries }}</p>
            </div>
            <div class="country_menu__item">
              <p>{{ $t('branch.numberOfCities') }}</p>
              <p>{{ country.number_of_cities }}</p>
            </div>
          </div>
        </div>
        <p v-if="$i18n.locale === 'ru'">{{ country.rus_lang_text }}</p>
        <p v-else>{{ country.eng_lang_text }}</p>
      </div>
      <!--      <img :src="country.country_map" />-->
    </div>
    <div class="solo_body">
      <img :src="country.country_map" width="590px" height="503px"/>
      <p v-if="$i18n.locale === 'ru'">{{ country.rus_lang_text }}</p>
      <p v-else>{{ country.eng_lang_text }}</p>
    </div>
    <nuxt-link :to="localePath('/Agencies')" class="see_all">
      {{ $t('branch.seeAll') }}<img src="../../assets/img/solo/go.png"/>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      country: [],
    };
  },
  methods: {},
  mounted() {
    this.$axios.get("http://185.100.65.231/api/country-detail/" + this.$route.params.id + "/")
      .then(response => (this.country = response.data));
  }
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/fonts.scss";
@import "../../assets/style/respond";

.solo {
  padding-bottom: 120px;
  padding-top: 130px;

  @include respond(phone) {
    padding-top: 60px;
    padding-bottom: 90px;
  }
}

p {
  @include normal;
  font-size: 16px;
  line-height: 19px;
  color: #131313;
  max-width: 488px;
  overflow-wrap: break-word;

  @include respond(tab-land) {
    padding: 0 30px;
  }

  @include respond(tab-land) {
    padding: 0 15px;
  }
}

.header_descr {
  display: block;
  //grid-template-columns: 520px 590px;
  //justify-content: space-between;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto 60px;

  .country_menu {
    background: #EDDDFF;
    //height: 227px;
    width: 590px;
    padding: 30px 20px;
    margin-bottom: 20px;
    margin-right: 20px;

    h1 {
      //@include medium;
      font-size: 40px;
      line-height: 47px;
      text-transform: uppercase;
      color: #623f99;
      margin-bottom: 20px;
    }

    //p {
    //  display: flex;
    //  align-items: center;
    //  margin-bottom: 10px;
    //  &:last-of-type {
    //    margin-bottom: 0;
    //  }
    //  img {
    //    margin-right: 10px;
    //  }
    //}
    &__items {

    }

    &__item {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      align-items: center;
      justify-content: space-between;
      padding: 5px 0;
      border-bottom: 1px solid #623F99;

      &:first-child {
        border-top: 1px solid #623f99;
      }

      p {
        display: block;

        &:last-child {
          text-align: right;
        }
      }
    }
  }

  @include respond(tab-land) {
    width: 767px;

    .country_menu {
      width: 100%;

      h1 {
        font-size: 26px;
        line-height: 32.7px;
      }

      &__item {
        align-items: start;
        p {
          padding: 0;
        }
      }
    }
  }

  @include respond(phone) {
    margin: 0 auto 40px;
  }
}

.country-row {
  display: flex;
  align-items: flex-start;

  @include respond(tab-land) {
    flex-direction: column;
    align-items: stretch;

    p {
      width: 100%;
      max-width: unset;
    }
  }
}

.solo_body {
  display: flex;
  flex-direction: row-reverse;
  //grid-template-columns: 590px 488px;
  //justify-content: space-between;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;
  padding-top: 60px;
  padding-bottom: 90px;

  p {
    text-align: right;
  }

  img {
    margin-left: 20px;
  }

  @include respond(tab-land) {
    width: 767px;
    flex-direction: column;
    align-items: center;

    img {
      margin-left: 0;
      margin-bottom: 20px;
    }

    p {
      text-align: left;
      width: 100%;
      max-width: unset;
    }
  }

  @include respond(phone) {
    padding-top: 0;
    padding-bottom: 40px;

    img {
      width: 343px;
      height: 301px;
    }
  }
}

.see_all {
  @include bold;
  font-size: 24px;
  line-height: 28px;
  text-align: center;
  text-decoration: none;
  text-transform: uppercase;
  color: #623f99;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  margin: 0 auto;
  width: 370px;

  img {
    margin-left: 10px;
  }

  @include respond(phone) {
    font-size: 18px;
    line-height: 22px;
    border-bottom: none !important;
    text-decoration: underline;
  }
}
</style>
