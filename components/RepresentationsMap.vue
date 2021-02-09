<template>
  <div class="representations">
    <h3 class="representations__title">
      {{ $t('branchesTitle') }}
    </h3>

    <div class="representations__map">
      <div v-for="count in countries">
        <img :src="count.country_position_on_map"
             alt=""
             v-if="country === count.eng_lang_country">
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
  </div>
</template>

<script>
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
    this.play();
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@import "../assets/style/respond";
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

  @include respond(phone) {
    &__title {
      font-size: 26px;
    }
  }
}

</style>
