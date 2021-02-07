<template>
  <div class="footer" id="footer">
    <h1>{{ $t('footerTitle') }}</h1>
    <div class="footer_bord" />
    <div class="content">
      <form class="form">
        <label for="name">{{ $t('footer.name') }}</label>
        <input id="name" type="text" :placeholder="$t('footer.namePlaceHolder')" v-model="full_name" />
        <label for="mobile">{{ $t('footer.contactData') }}</label>
        <input
          v-model="contact_data"
          id="mobile"
          type="text"
          :placeholder="$t('footer.phonePlaceHolder')"
        />
        <button @click="sendRequest" :class="btnState ? 'active' : ''">{{ $t('footer.btn') }}</button>
        <div class="social">
          <img src="../assets/img/main/tweet.png" />
          <img src="../assets/img/main/inst.png" />
          <img src="../assets/img/main/fb.png" />
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
        <div class="contacts__single">
          <h2><img src="../assets/img/main/telephone.png" />{{ $t('footer.phones') }}</h2>
          <a href="tel: +7 (727) 364 81 70">+7 (727) 364 81 70</a>
          <a href="tel: +7 (727) 364 88 88">+7 (727) 364 88 88</a>
        </div>
        <div class="contacts__single">
          <h2><img src="../assets/img/main/mail.png" />{{ $t('footer.mail') }}</h2>
          <p>info@cashsoswiftly.com</p>
        </div>
        <div class="contacts__single">
          <h2><img src="../assets/img/main/location.png" />{{ $t('footer.address') }}</h2>
          <p v-html="$t('footer.location')"></p>
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
      this.$axios.post("http://185.100.65.231/api/requests/", userInfo)
        .then(response => this.tempData = response.data)
        .catch(error => {
          this.errorMessage = error.message;
          console.log("ERROR!", error);
        });
    }
  },
  watch: {
    full_name() {
      if(this.full_name.length > 0 && this.contact_data.length > 0) {
        this.btnState = true;
      } else {
        this.btnState = false;
      }
    },
    contact_data() {
      if(this.full_name.length > 0 && this.contact_data.length > 0) {
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
}
.content {
  position: relative;
  width: 100%;
}
.form {
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding-top: 72px;
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
}
.contacts {
  position: absolute;
  top: 0;
  right: 0;
  width: 608px;
  height: 642px;
  background: #d0c5e0;
  padding-top: 166px;
  padding-left: 304px;
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
    left: -232px;
    z-index: 10;
  }
}
</style>
