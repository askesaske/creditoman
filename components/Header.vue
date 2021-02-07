<template>
  <div class="header_wrapper">
    <div class="header">
      <img class="logo" src="../assets/img/main/logo.png" @click="goHome" />
      <div class="navigation">
        <nuxt-link
          :to="localePath('/')"
          tag="a"
          class="navigation__link"
          title="главная"
          exact
        >
          {{ $t('header.home')}}
        </nuxt-link>
        <nuxt-link :to="localePath('/About')" tag="a" class="navigation__link" title="о нас">
          {{ $t('header.about')}}
        </nuxt-link>
        <nuxt-link
          :to="localePath('/Products')"
          tag="a"
          class="navigation__link"
          title="продукты"
        >
          {{ $t('header.products')}}
        </nuxt-link>
        <nuxt-link
          :to="localePath('/Agencies')"
          tag="a"
          class="agencies navigation__link"
          title="представительства"
        >
          {{ $t('header.branches')}}
          <div class="dropdown">
            <nuxt-link :to="localePath('/Agencies/' + count.id)"
                       v-for="count in countries" :key="count.id">{{ count.country}}</nuxt-link>
          </div>
        </nuxt-link>
        <nuxt-link
          :to="localePath('/Partnership')"
          tag="a"
          class="navigation__link"
          title="партнерство"
        >
          {{ $t('header.partner')}}
        </nuxt-link>
<!--        <nuxt-link-->
<!--          to="/Team"-->
<!--          tag="a"-->
<!--          class="navigation__link"-->
<!--          title="Наша команда"-->
<!--        >-->
<!--          Наша команда-->
<!--        </nuxt-link>-->
      </div>
      <div class="lang_local_wrapper" v-click-outside="hide">
        <div @click="toggleLang" class="lang_local">
          <img v-if="langState" src="../assets/img/main/rus.png" />
          <img v-else src="../assets/img/main/en.png" />
          <img src="../assets/img/main/lang_dropdown.png" />
        </div>
        <div v-if="langDrop" class="lang_local_wrapper__dropdown">
          <img v-if="langState" @click="changeLang('en')" src="../assets/img/main/en.png" />
          <img v-else @click="changeLang('ru')" src="../assets/img/main/rus.png" />
        </div>
      </div>
    </div>
    <div class="social">
      <div class="tweet">
        <img src="../assets/img/main/tweet.png" />
      </div>
      <div class="inst">
        <img src="../assets/img/main/inst.png" />
      </div>
      <div class="fb">
        <img src="../assets/img/main/fb.png" />
      </div>
    </div>
  </div>
</template>

<script>
import ClickOutside from "vue-click-outside";

export default {
  data: () => ({
    langDrop: false,
    countries: [],
    langState: true,
  }),
  directives: {
    ClickOutside
  },
  methods: {
    goHome() {
      this.$router.push("/");
    },
    toggleLang() {
      this.langDrop = !this.langDrop;
    },
    changeLang(langVal) {
      if(langVal === 'en') {
        this.$i18n.locale = 'en';
        this.langState = false;
      }
      if(langVal ==='ru') {
        this.$i18n.locale = 'ru';
        this.langState = true;
      }
      this.langDrop = false;
      // window.location.reload();
    },
    hide() {
      this.langDrop = false;
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
.header_wrapper {
  position: fixed;
  top: 0;
  left: 0;
  background: #ffffff;
  box-shadow: 0px 4px 10px rgba(146, 115, 194, 0.2);
  z-index: 999;
  width: 100%;
}
.header {
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  .logo {
    cursor: pointer;
  }
  .navigation {
    width: 809px;
    height: 70px;
    max-width: 100%;
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    &__link {
      @include normal;
      font-size: 16px;
      line-height: 19px;
      text-transform: uppercase;
      color: #131313;
      height: 45px;
      text-decoration: none;
      //&::before {
      //  display: block;
      //  content: attr(title);
      //  font-weight: bold;
      //  height: 0;
      //  overflow: hidden;
      //  visibility: hidden;
      //}
      &:hover {
        @include extbold;
        color: #623f99;
        border-bottom: 4px solid #623f99;
      }
    }
  }
  .lang_local_wrapper {
    position: relative;
    width: 118px;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    z-index: 999;
    &__dropdown {
      position: absolute;
      right: 0;
      bottom: -44px;
      width: 62px;
      height: 40px;
      border: 1px solid #623f99;
      border-radius: 4px;
      padding-left: 8px;
      background: #fff;
      cursor: pointer;
      display: flex;
      align-items: center;
    }
    .lang_local {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 62px;
      height: 40px;
      border: 1px solid #623f99;
      border-radius: 4px;
      cursor: pointer;
      img:last-of-type {
        margin-left: 6px;
      }
    }
  }
}
.agencies {
  position: relative;
  &:hover {
    .dropdown {
      display: unset;
      animation: dropdown_an 0.3s;
    }
  }
}
@keyframes dropdown_an {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
.dropdown {
  display: none;
  position: absolute;
  top: 35px;
  left: -9px;
  width: 200px;
  //height: 609px;
  padding: 25px 0;
  box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
  border-radius: 4px;
  background: #ffffff;
  border: 1px solid #131313;
  z-index: 999;
  &::before {
    content: "";
    position: absolute;
    width: 17px;
    height: 17px;
    background: #fff;
    border: 1px solid #131313;
    border-color: #131313 transparent transparent #131313;
    border-radius: 4px 0px 0px 0px;
    right: 17px;
    top: -9.7px;
    transform: rotate(45deg);
  }
  a {
    //@include medium;
    font-size: 16px;
    line-height: 19px;
    text-transform: uppercase;
    color: #623f99;
    padding: 6px 23px;
    display: block;
    text-decoration: none;
    margin-bottom: 4px;
    &:last-of-type {
      margin-bottom: 0;
    }
    &:hover {
      background: #d0c5e0;
    }
  }
}
.social {
  position: fixed;
  top: 209px;
  right: 0;
  height: 174px;
  z-index: 9999;
  .tweet,
  .inst,
  .fb {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 58px;
    height: 58px;
    cursor: pointer;
    img {
      transition: 0.4s;
    }
    &:hover {
      img {
        transform: scale(1.1);
      }
    }
  }
  .tweet {
    background: #41abe1;
    border-radius: 8px 0px 0px 0px;
  }
  .inst {
    background: #8f69cc;
  }
  .fb {
    background: #3d5d9a;
    border-radius: 0px 0px 0px 8px;
  }
}
</style>
