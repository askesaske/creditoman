<template>
  <transition name="modal">
    <div class="modal__mask">
      <div class="modal__wrapper">
        <div class="modal__container">

          <div class="modal__content">
            <div class="modal__img-box">
              <img :src="newsContent.img" alt="">
              <div class="modal__date">
                {{ newsContent.created_date | moment('YYYY - MM - DD') }}
              </div>
            </div>
            <h4 class="modal__heading" v-if="$i18n.locale === 'ru'">{{ newsContent.rus_lang_title }}</h4>
            <h4 class="modal__heading" v-else>{{ newsContent.eng_lang_title }}</h4>

            <div class="modal__text" v-html="newsContent.rus_lang_text" v-if="$i18n.locale === 'ru'"></div>
            <div class="modal__text" v-html="newsContent.eng_lang_text" v-else></div>
          </div>

          <button class="modal__button" @click="$emit('close')"></button>

        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  props: ['newsContent'],

}
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";

.modal {
  &__mask {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: table;
    transition: opacity 0.3s ease;
  }

  &__wrapper {
    display: table-cell;
    vertical-align: middle;
  }

  &__container {
    width: 1200px;
    margin: 0 auto;
    padding: 50px 0;
    background-color: #fff;
    border-radius: 4px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
    transition: all 0.3s ease;
    position: relative;
    max-height: 100vh;
    overflow: auto;
  }

  &__content {
    width: 790px;
    margin: 0 auto;
  }

  &__img-box {
    position: relative;
    margin-bottom: 80px;

    img {
      width: 100%;
    }
  }

  &__date {
    position: absolute;
    @include normal;
    font-size: 16px;
    color: #acacac;
    right: 0;
    top: calc(100% + 20px);
  }

  &__heading {
    @include bold;
    font-size: 24px;
    line-height: 30px;
    color: #623F99;
    margin-bottom: 20px;
  }

  &__text {
    @include normal;
    font-size: 16px;
    line-height: 20px;
    color: #131313;
    overflow-wrap: break-word;
  }

  &__button {
    position: absolute;
    width: 16px;
    height: 16px;
    background-image: url("../assets/img/main/exit.png");
    top: 24px;
    right: 24px;
    border: none;
    background-color: transparent;
    cursor: pointer;

    &:focus {
      outline: none;
    }
  }
}


/*
 * The following styles are auto-applied to elements with
 * transition="modal" when their visibility is toggled
 * by Vue.js.
 *
 * You can easily play with the modal transition by editing
 * these styles.
 */

.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>
