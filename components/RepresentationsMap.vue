<template>
  <div class="representations">
    <h3 class="representations__title">
      Представительства
    </h3>

    <div class="representations__map">
      <div v-for="count in countries">
        <img :src="count.country_position_on_map"
             alt=""
             v-if="country === count.country">
      </div>
      <div class="representations__countries">
        <img :src="c.country_flag"
             v-for="c in countries"
             alt=""
             @click="chooseCountry(c.country)"
             :class="country === c.country ? 'active' : ''">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      country: "Kazakhstan",
      countries: [],
    };
  },
  methods: {
    chooseCountry(str) {
      this.country = str;
    }
  },

  mounted() {
    this.$axios.get("http://185.100.65.231/api/country-list/")
      .then(response => (this.countries = response.data));
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
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
    position: relative;
  }

  &__countries {

    img {
      cursor: pointer;

      &:not(:last-child) {
        margin-right: 30px;
      }

      &.active {
        filter: drop-shadow(0px 0px 10px rgba(98, 63, 153, 0.5));
      }
    }
  }
}

</style>
