<template>
  <div class="agencies" v-if="worlds">
    <representations-map></representations-map>
    <div class="country" v-for="world in worlds">
      <h1>Страны {{ world.world }}</h1>
      <div class="custom_border"/>
      <div class="country__descr">
        <img width="590px" height="503px" :src="world.continent_img"/>
        <div class="text">
          <div class="text__single" v-for="country in world.country">
            <nuxt-link :to="'/Agencies/' + country.id" class="text__name">{{ country.country }}</nuxt-link>
            <p v-if="country.terminal_or_mobile.terminals !== null">{{ country.terminal_or_mobile.terminals }} терминалов</p>
            <p v-else-if="country.terminal_or_mobile.mobileapp !== null">
              Мобильное приложение
            </p>
            <p>{{ country.workers }} работников</p>
            <p>{{ country.clients }} клиентов</p>
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
    this.$axios.get("http://185.100.65.231/api/world-list/")
      .then(response => (this.worlds = response.data));
  },
};
</script>

<style lang="scss" scoped>
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
}
</style>
