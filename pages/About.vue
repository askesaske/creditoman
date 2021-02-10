<template>
  <div class="About">
    <h1 class="About__title" v-html="$t('about.heading')"></h1>
    <div class="custom_border"/>
    <div class="biography">
      <div class="biography__author">
        <div class="biography__box">
          <img
            class="biography__author__face"
            src="../assets/img/about/face.png"
          />
          <p class="biography__author__name">
            <span>{{ $t('about.ceoName') }}</span> <br/>
            {{ $t('about.ceoPosition') }}
          </p>
        </div>
        <div class="description">
          <p>
            {{ $t('about.biography1') }} <br/>
            <br/>

            {{ $t('about.biography2') }}<br/>
            <br/>

            {{ $t('about.biography3') }}<br/>
            <br/>

            {{ $t('about.biography4') }}<br/>
            <br/>

            {{ $t('about.biography5') }}<br/>
            <br/>

            {{ $t('about.biography6') }}<br/>
            <br/>

            {{ $t('about.biography7') }}<br/>
            <br/>
          </p>
        </div>
      </div>
    </div>
    <div class="priorities">
      <h1>{{ $t('about.valuesHeading') }}</h1>
      <div class="bord_title"/>
      <div class="grid_items">
        <div class="grid_items__single">
          <img src="../assets/img/main/honest.png"/>
          <h2>{{ $t('about.valueTitle1') }}</h2>
          <div class="bord_card"/>
          <p>
            {{ $t('about.valueText1') }}
          </p>
        </div>
        <div class="grid_items__single">
          <img src="../assets/img/main/clarity.png"/>
          <h2>{{ $t('about.valueTitle2') }}</h2>
          <div class="bord_card"/>
          <p>
            {{ $t('about.valueText2') }}
          </p>
        </div>
        <div class="grid_items__single">
          <img src="../assets/img/main/resp.png"/>
          <h2>{{ $t('about.valueTitle3') }}</h2>
          <div class="bord_card"/>
          <p>
            {{ $t('about.valueText3') }}
          </p>
        </div>
        <div class="grid_items__single">
          <img src="../assets/img/main/coop.png"/>
          <h2>{{ $t('about.valueTitle4') }}</h2>
          <div class="bord_card"/>
          <p>
            {{ $t('about.valueText4') }}
          </p>
        </div>
      </div>
    </div>
    <div class="cachsoswiftly">
      <h1>{{ $t('about.teamHeading') }}</h1>
      <div class="custom_border"/>
      <div class="cachsoswiftly__text">
        <p class="cachsoswiftly__subtitle" v-html="$t('about.teamText1')"></p>
        <p class="cachsoswiftly__subtitle" v-html="$t('about.teamText2')"></p>
      </div>
      <img
        class="cachsoswiftly__img"
        src="../assets/img/about/swiftly.png"
        ref="counter_div"
        v-if="$i18n.locale === 'ru'"
      />
      <img v-else src="../assets/img/about/swiftly-en.png" alt="">
    </div>
    <div class="counter" id="counter">
      <h1>{{ $t('about.todayHeading') }}</h1>

      <div class="counter__grid">
        <div class="counter__grid__single">
          <animate-number :number="terminalCount"></animate-number>
          <p>{{ $t('about.terminalCount') }}</p>
        </div>
        <div class="counter__grid__single">
          <animate-number :number="countryCount"></animate-number>
          <p>{{ $t('about.countryCount') }}</p>
        </div>
        <div class="counter__grid__single">
          <animate-number :number="staffCount"></animate-number>
          <p v-html="$t('about.staffCount')"></p>
        </div>
        <div class="counter__grid__single">
          <div>
            <animate-number :number="cashCount"></animate-number>
            <span>{{ $t('about.million') }}</span>
          </div>
          <p v-html="$t('about.creditCount')"></p>
        </div>
      </div>
    </div>
    <div class="video_cont">
      <button>
        {{ $t('about.profileBtn') }}<img src="../assets/img/about/drop.png"/>
      </button>
      <div class="video_cont__wrapper">
        <div class="video_cont__box">
          <div class="video_cont__overlay" @click="playVideo" v-if="overlay"></div>
          <video v-for="v in video" :src="v.video" controls id="video"></video>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AnimateNumber from "@/components/AnimateNumber";

export default {
  components: {
    AnimateNumber,
  },
  data: () => ({
    interval: false,
    counterPos: 0,
    userScroll: 0,
    terminalCount: 0,
    countryCount: 0,
    staffCount: 0,
    cashCount: 0,
    video: [],
    overlay: true
  }),


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
    playVideo() {
      this.overlay = false;
      document.getElementById('video').play();
    }
  },

  watch: {
    userScroll() {
      if (this.userScroll > this.counterPos) {
        this.terminalCount = 800;
        this.countryCount = 14;
        this.staffCount = 1000;
        this.cashCount = 7;
      }
      // console.log(this.userScroll + " " + this.counterPos);
    },
  },

  mounted() {
    window.addEventListener('scroll', e => this.userScroll = window.scrollY);
    var counterBox = document.getElementById('counter');
    this.counterPos = this.getPosition(counterBox);

    this.$axios.get("http://185.100.65.231/api/videos-list/")
      .then(response => (this.video = response.data));
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@import "../assets/style/respond";

img {
  max-width: 100%;
  width: auto;
}

.About {
  padding-top: 130px;
  overflow: hidden;

  &__title {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-transform: uppercase;
    text-align: center;
    color: #623f99;
  }

  @include respond(phone) {

    &__title {
      font-size: 26px;
      line-height: 32px;
    }
  }
}

.custom_border {
  width: 160px;
  border-bottom: 2px solid #623f99;
  margin: 10px auto 60px;
}

.biography {
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;
  display: flex;
  justify-content: flex-start;
  padding-top: 50px;
  height: 881px;
  margin-bottom: 120px;

  &__author {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    z-index: 5;

    &__face {
      margin-bottom: 20px;
    }

    &__name {
      //@include medium;
      font-size: 16px;
      line-height: 19px;
      color: #623f99;
      text-align: center;

      span {
        @include bold;
        text-transform: uppercase;
      }
    }
  }

  .description {
    position: absolute;
    width: 100vw;
    //height: 726px;
    background: #f8f2ff;
    top: -50px;
    left: 132px;
    padding: 90px 120px 90px 173px;
    z-index: -1;

    p {
      position: relative;
      @include normal;
      font-size: 18px;
      line-height: 21px;
      color: #544172;
      max-width: 895px;

      &::before {
        content: url("../assets/img/about/quotes.png");
        position: absolute;
        top: -30px;
        left: -40px;
        z-index: 999;
      }

      &::after {
        content: url("../assets/img/about/quotes.png");
        position: absolute;
        bottom: -10px;
        right: -30px;
        transform: rotate(180deg);
        z-index: 999;
      }

      @include respond(tab-land) {
        max-width: 767px;
        padding-right: 20px;
      }
    }
  }

  @include respond(tab-land) {
    height: 1300px;
  }

  @include respond(phone) {
    padding-top: 130px;
    margin-bottom: 0;

    &__author {
      width: 100%;
    }

    .description {
      position: unset;
      width: 100%;
      padding: 206px 16px 60px;
      text-align: center;

      p {
        font-size: 14px;
        line-height: 17.6px;
        max-width: 375px;
        margin: 0 auto;

        &:after, &:before {
          display: none;
        }
      }
    }

    &__box {
      position: absolute;
      top: -120px;

      img {
        width: 178px;
        height: 240px;
      }
    }
  }
}

//  priorities
.priorities {
  background-image: url("../assets/img/about/priority-bg.png");
  background-size: cover;
  background-repeat: no-repeat;
  padding: 120px 0;
  //height: 748px;

  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-align: center;
    text-transform: uppercase;
    color: #623f99;
  }

  .bord_title {
    width: 160px;
    margin: 10px auto 60px;
    border: 2px solid #623f99;
  }

  .grid_items {
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(4, 285px);
    justify-content: space-between;

    &__single {
      background: #ffffff;
      box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
      border-radius: 8px;
      height: 391px;
      padding: 30px 20px;
      text-align: center;

      h2 {
        //@include medium;
        font-size: 24px;
        line-height: 28px;
        text-align: center;
        text-transform: uppercase;
        color: #623f99;
        margin-top: 30px;
        margin-bottom: 10px;
      }

      .bord_card {
        border: 1px solid #623f99;
        width: 80px;
        margin: 0px auto 20px;
      }

      p {
        @include normal;
        font-size: 16px;
        line-height: 19px;
        color: #131313;
      }
    }

    @include respond(tab-land) {
      width: 768px;
      max-width: unset;
      grid-template-columns: repeat(2, 1fr);
      grid-gap: 20px;
    }
  }

  @include respond(tab-land) {
    //height: 1150px;
  }

  @include respond(phone) {
    padding: 120px 0 60px;
    h1 {
      font-size: 26px;
      line-height: 32px;
    }
    .bord_title {
      width: 68px;
      margin: 5px auto 32px;
    }

    .grid_items {
      width: unset;
      max-width: 375px;
      padding-left: 15px;
      padding-right: 15px;
      grid-template-columns: repeat(1, 1fr);
    }
  }
}

.cachsoswiftly {
  background: #f8f2ff;
  padding-top: 60px;
  padding-bottom: 120px;
  text-align: center;

  h1 {
    @include bold;
    font-size: 40px;
    line-height: 47px;
    text-transform: uppercase;
    color: #623f99;
    text-align: center;
  }

  .custom_border {
    margin-bottom: 67px;
  }

  &__text {
    margin-bottom: 40px;
  }

  &__subtitle {
    @include normal;
    font-size: 24px;
    line-height: 30px;
    text-align: center;
    color: #131313;

    &:not(:last-child) {
      margin-bottom: 20px;
    }
  }

  @include respond(phone) {
    h1 {
      font-size: 26px;
    }

    .custom_border {
      margin-bottom: 30px;
    }

    &__subtitle {
      font-size: 14px;
      line-height: 17px;
      text-align: center;
      max-width: 375px;
      padding: 0 15px;
      margin-left: auto;
      margin-right: auto;
    }
  }
}

.counter {
  background-image: url("../assets/img/about/bg.png");
  background-size: cover;
  background-repeat: no-repeat;
  padding-top: 90px;
  padding-bottom: 60px;

  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    color: #d5dd25;
    text-align: center;
  }

  &__test {

  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(4, 285px);
    justify-content: space-between;
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;
    padding-top: 30px;

    &__single {
      text-align: center;
      height: 190px;
      background: #ffffff;
      box-shadow: 0px 4px 16px rgba(98, 63, 153, 0.25);
      border-radius: 8px;
      padding-top: 40px;

      span {
        @include bold;
        font-size: 50px;
        line-height: 59px;
        color: #623f99;
        margin-bottom: 5px;
      }

      p {
        @include normal;
        font-size: 24px;
        line-height: 28px;
        text-align: center;
        color: #131313;
      }
    }
  }

  @include respond(tab-land) {
    &__grid {
      max-width: unset;
      width: 767px;
      grid-template-columns: repeat(2, 1fr);
      grid-gap: 20px;
    }
  }

  @include respond(phone) {
    padding-top: 60px;

    h1 {
      font-size: 26px;
      line-height: 32px;
      margin-bottom: 30px;
    }

    &__grid {
      max-width: 375px;
      padding: 0 15px;
      grid-template-columns: repeat(1, 1fr);
      grid-gap: 20px;
    }
  }
}

.video_cont {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 120px 0;

  button {
    display: flex;
    align-items: center;
    justify-content: center;
    @include bold;
    font-size: 18px;
    line-height: 21px;
    text-decoration-line: underline;
    text-transform: uppercase;
    color: #623f99;
    border: none;
    outline: none;
    width: 346px;
    height: 56px;
    background: #d5dd25;
    box-shadow: 0px 2px 12px rgba(213, 221, 37, 0.25);
    border-radius: 30px;
    cursor: pointer;
    margin-bottom: 60px;

    img {
      margin-left: 13px;
    }
  }

  &__wrapper {
    padding: 50px;
    background-color: rgba(146, 115, 194, 0.5);
    border-radius: 4px;
  }

  &__box {
    position: relative;

    video {
      position: relative;
      z-index: 1;

      &:focus {
        outline: none;
      }
    }
  }

  &__overlay {
    cursor: pointer;
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url("../assets/img/about/video-bg.png");
    background-size: cover;
    background-repeat: no-repeat;
    z-index: 2;
  }

  @include respond(phone) {
    &__wrapper {
      padding: 30px 18px;
    }

    &__box video {
      max-width: 307px;
      width: auto;
    }
  }
}
</style>
