<template>
  <div class="footer" id="footer">
    <h1>{{ $t('footerTitle') }}</h1>
    <div class="footer_bord"/>
    <div class="content">
      <form class="form">
        <div class="form__inside">
          <label for="name">{{ $t('footer.name') }}</label>
          <input id="name" type="text" :placeholder="$t('footer.namePlaceHolder')" v-model="full_name"/>
          <label for="mobile">{{ $t('footer.contactData') }}</label>
          <input
            v-model="contact_data"
            id="mobile"
            type="text"
            :placeholder="$t('footer.phonePlaceHolder')"
          />
          <button @click="sendRequest" :class="btnState ? 'active' : ''">{{ $t('footer.btn') }}</button>
          <div class="social">
            <a href="https://www.linkedin.com/company/cashsoswiftly-llc/?originalSubdomain=ru">
              <img src="../assets/img/main/linkedin.png"/>
            </a>
            <a href="https://www.instagram.com/creditomat.md/?hl=ru">
              <img src="../assets/img/main/inst.png"/>
            </a>
          </div>
        </div>
      </form>
      <div class="contacts">
        <iframe
          class="contacts__map"
          src="https://yandex.com/map-widget/v1/?um=constructor%3Af2ffd857abdc9416cfe560b26ee24eda4417b72452cde64cdd7d914edf3753ea&amp;source=constructor"
          width="500"
          height="500"
          frameborder="0"
        ></iframe>
        <div class="contacts__container">
          <div class="contacts__single">
            <h2><img src="../assets/img/main/telephone.png"/>{{ $t('footer.phones') }}</h2>
            <a href="tel: +7 (727) 364 81 70">+7 (727) 364 81 70</a>
            <a href="tel: +7 (727) 364 88 88">+7 (727) 364 88 88</a>
          </div>
          <div class="contacts__single">
            <h2><img src="../assets/img/main/mail.png"/>{{ $t('footer.mail') }}</h2>
            <p>info@cashsoswiftly.com</p>
          </div>
          <div class="contacts__single">
            <h2><img src="../assets/img/main/location.png"/>{{ $t('footer.address') }}</h2>
            <p v-html="$t('footer.location')"></p>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      full_name: "",
      contact_data: "",
      tempData: null,
      errorMessage: "",
      btnState: false,
    };
  },
  methods: {
    sendRequest() {
      const userInfo = {
        full_name: this.full_name,
        contact_data: this.contact_data,
      };
      this.$axios.post("https://cashsoswiftly.com/api/requests/", userInfo)
        .then(response => this.tempData = response.data)
        .catch(error => {
          this.errorMessage = error.message;
          console.log("ERROR!", error);
        });
    }
  },
  watch: {
    full_name() {
      if (this.full_name.length > 0 && this.contact_data.length > 0) {
        this.btnState = true;
      } else {
        this.btnState = false;
      }
    },
    contact_data() {
      if (this.full_name.length > 0 && this.contact_data.length > 0) {
        this.btnState = true;
      } else {
        this.btnState = false;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
@import "../assets/style/respond";

.footer {
  background: #544172;
  height: 881px;
  padding-top: 120px;

  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-transform: uppercase;
    color: #d5dd25;
    text-align: center;
  }

  .footer_bord {
    width: 160px;
    margin: 10px auto 60px;
    border-bottom: 2px solid #d5dd25;
  }

  @include respond(tab-land) {
    height: unset;

    .footer_bord {
      margin-bottom: 40px;
    }
  }

  @include respond(phone) {
    padding-top: 90px;

    h1 {
      font-size: 26px;
      line-height: 32px;
    }

    .footer_bord {
      margin: 5px auto 40px;
    }
  }
}

.content {
  position: relative;
  width: 100%;
}

.form {
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;
  padding-top: 72px;

  &__inside {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  label {
    //@include medium;
    font-size: 16px;
    line-height: 19px;
    text-transform: uppercase;
    color: #ffffff;
    margin-bottom: 3px;
  }

  input {
    padding-left: 16px;
    width: 380px;
    height: 44px;
    border: 1px solid rgba($color: #ffffff, $alpha: 0.5);
    border-radius: 8px;
    background: transparent;
    outline: none;
    @include normal;
    font-size: 16px;
    line-height: 19px;
    color: #ffffff;

    &:first-of-type {
      margin-bottom: 34px;
    }
  }

  ::placeholder {
    @include normal;
    font-size: 16px;
    line-height: 19px;
    color: #ffffff;
    opacity: 0.3;
  }

  button {
    @include bold;
    font-size: 18px;
    line-height: 21px;
    text-transform: uppercase;
    color: #5c4a79;
    margin-top: 68px;
    width: 296px;
    height: 56px;
    background: rgba(255, 255, 255, 0.5);
    border-radius: 30px;
    border: none;
    outline: none;
    cursor: pointer;
    transition: 0.3s;

    &.active {
      color: #623f99;
      background: #d5dd25;
      box-shadow: 0px 2px 12px rgba(213, 221, 37, 0.25);
    }
  }

  .social {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    margin-top: 188px;

    img {
      cursor: pointer;
      margin-right: 30px;
      transition: all .2s;

      &:hover {
        transform: scale(1.1);
      }
    }
  }

  @include respond(tab-land) {
    width: 767px;
    padding-top: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding-bottom: 300px;

    .social {
      margin-top: 80px;
    }
  }

  @include respond(phone) {
    width: unset;
    max-width: 375px;
    padding-left: 15px;
    padding-right: 15px;
    padding-bottom: 150px;

    &__inside {
      width: 100%;
    }

    input {
      width: 100%;
      font-size: 14px;
    }

    ::placeholder {
      font-size: 14px;
    }

    button {
      width: 100%;
      height: 46px;
      font-size: 16px;
      margin-top: 60px;
    }

    .social {
      margin: 80px auto 0;
    }
  }
}

.contacts {
  position: absolute;
  top: 0;
  right: 0;
  width: 608px;
  height: 642px;
  background: #d0c5e0;
  padding-top: 166px;
  padding-left: 335px;

  &__single {
    margin-bottom: 50px;

    &:last-of-type {
      margin-bottom: 0;
    }

    h2 {
      display: flex;
      align-items: center;
      @include bold;
      font-size: 16px;
      line-height: 19px;
      text-transform: uppercase;
      color: #5c4a79;
      margin-bottom: 12px;

      img {
        margin-right: 10px;
      }
    }

    a,
    p {
      @include normal;
      font-size: 16px;
      line-height: 19px;
      color: #5c4a79;
      text-decoration: none;
      display: block;

      &:first-of-type {
        margin-bottom: 10px;
      }
    }
  }

  &__map {
    position: absolute;
    top: 72px;
    left: -205px;
    z-index: 10;
  }

  @include respond(tab-land) {
    position: relative;
    width: unset;
    height: unset;
    padding-top: 390px;
    padding-bottom: 60px;
    padding-left: 0;

    &__container {
      width: 500px;
      margin: 0 auto;
    }

    &__map {
      top: -30%;
      left: 50%;
      transform: translateX(-50%);
    }
  }

  @include respond(phone) {
    padding-top: 230px;

    &__container {
      max-width: 375px;
      width: unset;
      padding-left: 104px;
    }

    &__map {
      width: 262px;
      height: 262px;
      top: -70px;
    }
  }
}
</style>
