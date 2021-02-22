<template>
  <div class="agencies" v-if="worlds">
    <representations-map></representations-map>
    <div class="country" v-for="world in worlds">
      <h1 v-if="$i18n.locale === 'ru'">{{ world.rus_lang_world }}</h1>
      <h1 v-else>{{ world.eng_lang_world }}</h1>
      <div class="custom_border"/>
      <div class="country__descr">
        <img width="590px" height="503px" :src="world.continent_img"/>
        <div class="text">
          <div class="text__single" v-for="country in world.country">
            <nuxt-link :to="localePath('/Agencies/' + country.id)" class="text__name" v-if="$i18n.locale === 'ru'">{{ country.rus_lang_country }}</nuxt-link>
            <nuxt-link :to="localePath('/Agencies/' + country.id)" class="text__name" v-else>{{ country.eng_lang_country }}</nuxt-link>
            <div class="text__list"
                 v-if="(country.rus_lang_country !== null || country.eng_lang_country !== null) && country.workers !== null && country.clients !== null">
              <p v-if="$i18n.locale === 'ru'">{{ country.rus_lang_terminal_or_mobile }} </p>
              <p v-else>{{ country.eng_lang_terminal_or_mobile }} </p>
              <p v-if="$i18n.locale === 'ru'">{{ country.workers }} работников</p>
              <p v-else>{{ country.workers }} employees</p>
              <p v-if="$i18n.locale === 'ru'">{{ country.clients }} клиентов</p>
              <p v-else>{{ country.clients }} clients</p>
            </div>
            <div class="text__target" v-else>
              <p v-if="$i18n.locale === 'ru'">Таргет 2021</p>
              <p v-else>Target 2021</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import RepresentationsMap from "@/components/RepresentationsMap";

export default {
  components: {
    RepresentationsMap,
  },
  data() {
    return {
      worlds: [],
    };
  },
  mounted() {
    this.$axios.get("http://185.22.67.25/api/world-list/")
      .then(response => (this.worlds = response.data));
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/respond";
@import "../../assets/style/fonts.scss";

.agencies {
  padding-top: 130px;
  padding-bottom: 120px;
}

.custom_border {
  width: 160px;
  border-bottom: 2px solid #623f99;
  margin: 0 auto 60px;
}

.europe {
  .country__descr {
    grid-template-columns: 1fr 590px !important;
  }
}

.africa {
  display: flex !important;
  flex-direction: column !important;
  align-items: center !important;
  justify-content: center !important;
}

.country {
  $e: &;
  padding-top: 120px;

  &:nth-child(odd) {
    #{$e}__descr {
      flex-direction: row-reverse;
      img {
        margin-right: 0;
        margin-left: 60px;
      }
      .text__single:first-child {
        grid-column: 2 / 3;
        grid-row: 1 / 2;
      }
    }
  }

  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-transform: uppercase;
    text-align: center;
    color: #623f99;
  }

  &__descr {
    display: flex;
    align-items: flex-start;
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;

    img {
      margin-right: 60px;
    }
  }

  @include respond(tab-land) {
    &:nth-child(odd) {
      #{$e}__descr {
        flex-direction: column;
        img {
          margin-left: 0;
        }
        .text__single:first-child {
          grid-column: 1 / 2;
          grid-row: 1 / 2;
        }
      }
    }

    &__descr {
      flex-direction: column;
      align-items: center;
      width: 767px;
      margin: 0 auto;

      img {
        margin-right: 0;
        margin-bottom: 40px;
      }
    }
  }

  @include respond(phone) {
    padding-top: 90px;

    h1 {
      font-size: 26px;
      line-height: 32.7px;
    }

    h1 + .custom_border {
      width: 70px;
      margin-bottom: 30px;
    }

    &__descr {
      width: unset;
      max-width: 375px;

      img {
        width: 343px;
        height: 301px;
      }
    }
  }
}

.text {
  display: grid;
  grid-template-columns: repeat(2, 203px);
  grid-row-gap: 60px;
  width: 100%;
  justify-content: space-between;

  &__name {
    display: block;
    font-size: 24px;
    line-height: 30px;
    color: #623f99;
    margin-bottom: 12px;
    text-transform: uppercase;
    text-decoration: none;
    @include bold;
  }

  &__single {
    text-align: center;

    p {
      @include normal;
      font-size: 16px;
      line-height: 19px;
      color: #131313;
      margin-bottom: 8px;

      &:last-of-type {
        margin-bottom: 0;
      }
    }
  }

  @include respond(tab-land) {
    justify-content: space-around;
  }

  @include respond(phone) {
    grid-gap: 40px;
    grid-template-columns: repeat(2, 1fr);
    padding: 0 15px;
    justify-content: unset;

    &__name {
      font-size: 14px;
      line-height: 17.6px;
    }

    &__single {
      text-align: center;

      p {
        font-size: 14px;
        line-height: 17.6px;
        margin-bottom: 6px;

        &:last-of-type {
          margin-bottom: 0;
        }
      }
    }
  }
}
</style>
