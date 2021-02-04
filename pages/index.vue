<template>
  <div class="index">
    <div class="welcome">
      <div class="welcome__content">
        <h1>
          Микрокредит: <br/>
          Быстрый кредит в 3 клика
        </h1>
        <div class="custom_border"/>
        <p>Мы Ваше решение в сложных ситуациях</p>
        <button>Связаться с нами</button>
      </div>
    </div>
    <div class="sponsors">
      <div class="sponsors__wrapper">
        <img src="../assets/img/main/bottomLogo1.png"/>
        <img src="../assets/img/main/bottomLogo2.png"/>
        <img src="../assets/img/main/bottomLogo3.png"/>
        <img src="../assets/img/main/bottomLogo4.png"/>
      </div>
    </div>
    <div class="about">
      <div class="fixed__bg"/>
      <div class="about__content">
        <h1>О нас</h1>
        <p>
          Мы – <span>единственная во всем мире компания</span>, которая может
          выдать заем, не задавая ни одного вопроса, всего за 30 секунд!
        </p>
        <p>
          Ценность нашей компании в <span>уникальном оборудовании и ПО</span>,
          которые <span>облегчают и ускоряют процесс</span> выдачи кредита по
          сравнению с традиционными методами.
        </p>
        <p>
          Программа терминала
          <span>индивидуально подбирает сумму выдачи</span> и процент возврата с
          учетом кредитной истории заемщика.
        </p>
        <p>
          «CASHSOSWIFTLY» обеспечивает <span>развитие и функционирование</span>
          самой широкой сети терминалов по выдаче мгновенных займов по всему
          миру.
        </p>
      </div>
    </div>
    <div class="products">
      <h1>Наши продукты</h1>
      <div class="cus_bord"/>
      <div class="products__grid">
        <nuxt-link
          tag="div"
          to="/Products"
          class="products__grid__single grid_first"
        >
          <h2>DoZP.kz</h2>
          <div class="grid_bord"/>
          <p>
            Мобильное приложение по выдаче онлайн займов
          </p>
        </nuxt-link>
        <nuxt-link
          tag="div"
          to="/Products"
          class="products__grid__single grid_second"
        >
          <h2>Терминалы</h2>
          <div class="grid_bord"/>
          <p>
            Специально оборудованный <br>
            терминал <br>
            по выдаче займа <br>
            за 30 секунд
          </p>
        </nuxt-link>
        <nuxt-link
          tag="div"
          to="/Products"
          class="products__grid__single grid_third"
        >
          <h2>Click Advance</h2>
          <div class="grid_bord"/>
          <p>
            Мобильное приложение по выдаче аванса сотрудникам компании
          </p>
        </nuxt-link>
      </div>
    </div>

    <div class="feature">
      <p class="feature__text">
        Мы, CASHSOSWIFTLY, <span>приносим две безусловные выгоды </span>обществу в странах, где мы работаем.
      </p>

      <h4 class="feature__title">
        Люди, которые занимают деньги, НЕ будут воровать, грабить и каким-либо образом нарушать закон. Люди, которые
        занимают деньги, учатся финансовой ответственности при минимальных издержках.
      </h4>

      <div class="feature__items">
        <p class="feature__item">
          Мы отдаем должное людям. Мы безоговорочно доверяем <br>
          нашему клиенту, когда порой ему никто не доверяет
        </p>
        <p class="feature__item">
          Мы стараемся помочь и помогаем, когда нет другой помощи
        </p>
        <p class="feature__item">
          Наши проценты никогда не растут безмерно, как в <br>
          банковских кредитах. Поэтому, даже когда наш клиент <br>
          нуждается, он тем не менее вернет сумму, меньшую по <br>
          сравнению с банковским кредитом
        </p>
      </div>
    </div>

    <div class="main-features">
      <h3 class="main-features__title">
        Микрофинансовые организации дает обществу следующие <br>
        основные преимущества
      </h3>

      <div class="main-features__row">
        <div class="main-features__box">
          <img src="../assets/img/main/cash.png" alt="">
          <h5>
            Доступ к деньгам
          </h5>
          <p>
            Очень часто банки просто
            не предоставляют кредиты тем, у кого мало активов или вообще не имеются таковые. И, как правило, банки
            не занимаются выдачей кредитов на небольшие суммы, которые обычно ассоциируются с микрофинансированием. Наш
            бизнес основан на философии, согласно которой даже небольшая сумма кредита может помочь разорвать порочный
            круг бедности.
          </p>
        </div>
        <div class="main-features__box">
          <img src="../assets/img/main/investment.png" alt="">
          <h5>
            Лучшие условия погашения
          </h5>
          <p>
            Люди, которые занимают небольшие суммы денег, как правило, более ответственно относятся к выплате своих
            долгов, потому что они действуют более осторожно.
          </p>
        </div>
        <div class="main-features__box">
          <img src="../assets/img/main/online-learning.png" alt="">
          <h5>
            Дополнительное образование и здоровье
          </h5>
          <p>
            Когда люди в беде, когда им срочно нужны быстрые деньги - для оплаты образования, для оплаты медицинских
            услуг- у людей нет времени ждать. Таким образом, мы даем возможность нашим клиентам оплачивать быстрее,
            когда им действительно нужны деньги.
          </p>
        </div>
      </div>
    </div>

    <div class="support_txt">
      <h1>Наши миссия</h1>
      <div class="support_txt__bord"/>
      <p class="support_txt__subtitle">
        Мы стремимся быть ведущей компанией в мире,
        <span>ориентированной на клиентов</span>, предлагая физическим лицам удобный
        доступ к инновационным и конкурентоспособным финансовым продуктам посредством различных каналов
      </p>
      <div class="advantages_wrapper">
        <div class="advantages">
          <div class="advantages__single">
            <div class="img_title">
              <img src="../assets/img/main/111.png"/>
              <h2>Мы превосходим все ожидания</h2>
            </div>
            <p>
              Мы стремимся упростить, улучшить и удивить партнеров и клиентов, с которыми мы работаем. Мы жаждем
              совершенствоваться, нам любопытно, мы привержены делу, мы заботимся. Вот почему мы ставим наших клиентов
              на первое место
            </p>
          </div>
          <div class="advantages__single">
            <div class="img_title">
              <img src="../assets/img/main/222.png"/>
              <h2>Мы ищем лучшее</h2>
            </div>
            <p>
              Мы сочетаем наш опыт с желанием учиться. Мы нацелены на инновации, чтобы наши продукты всегда опережали
              продукты конкурентов. Мы стремимся улучшить каждый аспект нашей деятельности за счет творческого подхода
              нашей команды
            </p>
          </div>
          <div class="advantages__single">
            <div class="img_title">
              <img src="../assets/img/main/333.png"/>
              <h2>
                Мы ценим <br/>
                различия
              </h2>
            </div>
            <p>
              Многообразие и различия – вот, что делает нас сильнее. Мы стремимся привлечь самый широкий круг людей и
              создать среду, в которой они могут процветать. Наша команда профессионалов – вот, что отличает нас, и мы
              приветствуем вклад каждого из членов команды
            </p>
          </div>
          <div class="advantages__single">
            <div class="img_title">
              <img src="../assets/img/main/444.png"/>
              <h2>совершенствуем <br>
                ся вместе</h2>
            </div>
            <p>
              Мы - семья, которая ценит честность и добросовестность. В этой семье мы предоставляем каждому возможность
              достигать наилучших результатов, мы работаем вместе и вовлекаемся в процесс как одна сплоченная команда.
              Вместе мы добиваемся большего
            </p>
          </div>
        </div>
      </div>
    </div>

    <div class="representations">

      <h3 class="representations__title">
        Представительства
      </h3>

      <div class="representations__map">
        <img src="../assets/img/countries/kazakhstan.png"
             alt=""
             v-if="country === 'Kazakhstan'">
        <img src="../assets/img/countries/kyrgyzstan.png"
             alt=""
             v-if="country === 'Kyrgyzstan'">
        <img src="../assets/img/countries/azerbaijan.png"
             alt=""
             v-if="country === 'Azerbaijan'">
        <img src="../assets/img/countries/ukraine.png"
             alt=""
             v-if="country === 'Ukraine'">
        <img src="../assets/img/countries/moldova.png"
             alt=""
             v-if="country === 'Moldova'">
        <img src="../assets/img/countries/mongolia.png"
             alt=""
             v-if="country === 'Mongolia'">
        <img src="../assets/img/countries/romania.png"
             alt=""
             v-if="country === 'Romania'">
        <img src="../assets/img/countries/vietnam.png"
             alt=""
             v-if="country === 'Vietnam'">
        <img src="../assets/img/countries/philippines.png"
             alt=""
             v-if="country === 'Philippines'">
        <img src="../assets/img/countries/dominican-republic.png"
             alt=""
             v-if="country === 'Dominican'">
        <img src="../assets/img/countries/albania.png"
             alt=""
             v-if="country === 'Albania'">
        <img src="../assets/img/countries/serbia.png"
             alt=""
             v-if="country === 'Serbia'">
        <img src="../assets/img/countries/sri-lanka.png"
             alt=""
             v-if="country === 'Sri-lanka'">
        <img src="../assets/img/countries/namibia.png"
             alt=""
             v-if="country === 'Namibia'">
        <img src="../assets/img/countries/panama.png"
             alt=""
             v-if="country === 'Panama'">
        <img src="../assets/img/countries/guatemala.png"
             alt=""
             v-if="country === 'Guatemala'">
        <img src="../assets/img/countries/republik-des-kongo.png"
             alt=""
             v-if="country === 'Des-kongo'">
        <img src="../assets/img/countries/ecuador.png"
             alt=""
             v-if="country === 'Ecuador'">
        <img src="../assets/img/countries/mexiko.png"
             alt=""
             v-if="country === 'Mexiko'">
        <img src="../assets/img/countries/bosnia-and-herzegovina.png"
             alt=""
             v-if="country === 'Bosnia'">
        <img src="../assets/img/countries/republic-of-macedonia.png"
             alt=""
             v-if="country === 'Macedonia'">
        <img src="../assets/img/countries/columbia.png"
             alt=""
             v-if="country === 'Columbia'">

        <div class="representations__countries">
          <img src="../assets/img/countries/kazakhstan-logo.png"
               alt=""
               @click="chooseCountry('Kazakhstan')"
               :class="country === 'Kazakhstan' ? 'active' : ''">
          <img src="../assets/img/countries/kyrgyzstan-logo.png"
               alt=""
               @click="chooseCountry('Kyrgyzstan')"
               :class="country === 'Kyrgyzstan' ? 'active' : ''">
          <img src="../assets/img/countries/azerbaijan-logo.png"
               alt=""
               @click="chooseCountry('Azerbaijan')"
               :class="country === 'Azerbaijan' ? 'active' : ''">
          <img src="../assets/img/countries/ukraine-logo.png"
               alt=""
               @click="chooseCountry('Ukraine')"
               :class="country === 'Ukraine' ? 'active' : ''">
          <img src="../assets/img/countries/moldova-logo.png"
               alt=""
               @click="chooseCountry('Moldova')"
               :class="country === 'Moldova' ? 'active' : ''">
          <img src="../assets/img/countries/mongolia-logo.png"
               alt=""
               @click="chooseCountry('Mongolia')"
               :class="country === 'Mongolia' ? 'active' : ''">
          <img src="../assets/img/countries/romania-logo.png"
               alt=""
               @click="chooseCountry('Romania')"
               :class="country === 'Romania' ? 'active' : ''">
          <img src="../assets/img/countries/vietnam-logo.png"
               alt=""
               @click="chooseCountry('Vietnam')"
               :class="country === 'Vietnam' ? 'active' : ''">
          <img src="../assets/img/countries/philippines-logo.png"
               alt=""
               @click="chooseCountry('Philippines')"
               :class="country === 'Philippines' ? 'active' : ''">
          <img src="../assets/img/countries/dominican-republic-logo.png"
               alt=""
               @click="chooseCountry('Dominican')"
               :class="country === 'Dominican' ? 'active' : ''">
          <img src="../assets/img/countries/albania-logo.png"
               alt=""
               @click="chooseCountry('Albania')"
               :class="country === 'Albania' ? 'active' : ''">
          <img src="../assets/img/countries/serbia-logo.png"
               alt=""
               @click="chooseCountry('Serbia')"
               :class="country === 'Serbia' ? 'active' : ''">
          <img src="../assets/img/countries/sri-lanka-logo.png"
               alt=""
               @click="chooseCountry('Sri-lanka')"
               :class="country === 'Sri-lanka' ? 'active' : ''">
          <img src="../assets/img/countries/namibia-logo.png"
               alt=""
               @click="chooseCountry('Namibia')"
               :class="country === 'Namibia' ? 'active' : ''">
          <img src="../assets/img/countries/panama-logo.png"
               alt=""
               @click="chooseCountry('Panama')"
               :class="country === 'Panama' ? 'active' : ''">
          <img src="../assets/img/countries/guatemala-logo.png"
               alt=""
               @click="chooseCountry('Guatemala')"
               :class="country === 'Guatemala' ? 'active' : ''">
          <img src="../assets/img/countries/republik-des-kongo-logo.png"
               alt=""
               @click="chooseCountry('Des-kongo')"
               :class="country === 'Des-kongo' ? 'active' : ''">
          <img src="../assets/img/countries/ecuador-logo.png"
               alt=""
               @click="chooseCountry('Ecuador')"
               :class="country === 'Ecuador' ? 'active' : ''">
          <img src="../assets/img/countries/mexiko-logo.png"
               alt=""
               @click="chooseCountry('Mexiko')"
               :class="country === 'Mexiko' ? 'active' : ''">
          <img src="../assets/img/countries/bosnia-and-herzegovina-logo.png"
               alt=""
               @click="chooseCountry('Bosnia')"
               :class="country === 'Bosnia' ? 'active' : ''">
          <img src="../assets/img/countries/republic-of-macedonia-logo.png"
               alt=""
               @click="chooseCountry('Macedonia')"
               :class="country === 'Macedonia' ? 'active' : ''">
          <img src="../assets/img/countries/british-columbia-logo.png"
               alt=""
               @click="chooseCountry('Columbia')"
               :class="country === 'Columbia' ? 'active' : ''">
        </div>
      </div>
    </div>

    <div class="articles">
      <h1>новости и события</h1>
      <div class="articles_bord"/>
      <div class="articles__grid">
        <div class="single_item" @click="showModal = true">
          <img src="../assets/img/main/st1.png"/>
          <p class="single_item__date">2020-11-27</p>
          <h2 class="single_item__title">Административные условия</h2>
          <p class="single_item__descr">
            Значимость этих проблем настолько очевидна, что реализация
            намеченных плановых заданий позволяет выполнять важные задания по
            разработке позиций, занимаемых участниками в отношении поставленных
            задач.
          </p>
          <p class="single_item__more">
            Читать больше
          </p>
        </div>
        <div class="single_item">
          <img src="../assets/img/main/st2.png"/>
          <p class="single_item__date">2020-11-27</p>
          <h2 class="single_item__title">
            Стремящиеся вытеснить традиционное производство
          </h2>
          <p class="single_item__descr">
            Безусловно, перспективное планирование говорит о возможностях новых
            принципов формирования материально-технической и кадровой базы.
          </p>
          <p class="single_item__more">
            Читать больше
          </p>
        </div>
        <div class="single_item">
          <img src="../assets/img/main/st3.png"/>
          <p class="single_item__date">2020-11-27</p>
          <h2 class="single_item__title">
            Укрепление и развитие структуры требуют определения
          </h2>
          <p class="single_item__descr">
            Значимость этих проблем настолько очевидна, что постоянный
            количественный рост и сфера нашей активности обеспечивает широкому
            кругу (специалистов) участие в формировании направлений
            прогрессивного развития.
          </p>
          <p class="single_item__more">
            Читать больше
          </p>
        </div>
      </div>
    </div>
    <news-modal v-if="showModal" @close="showModal = false">
      <h3 slot="header">custom header</h3>
    </news-modal>
  </div>
</template>

<script>
import NewsModal from "@/components/NewsModal";

export default {
  components: {
    NewsModal,
  },
  data() {
    return {
      country: "Kazakhstan",
      showModal: false,
    };
  },
  methods: {
    chooseCountry(str) {
      this.country = str;
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";

.index {
  padding-top: 70px;
}

// welcome
.welcome {
  position: relative;
  background-image: url("../assets/img/main/bg.png");
  background-size: 100% 100%;
  padding-top: 173px;
  height: 610px;
  width: 100%;

  &__content {
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;

    h1 {
      @include bold;
      font-size: 60px;
      line-height: 70px;
      color: #ffffff;
      text-shadow: 0px 0px 4px rgba(0, 0, 0, 0.5);
    }

    .custom_border {
      margin-top: 10px;
      margin-bottom: 20px;
      width: 200px;
      border: 2px solid #d5dd25;
    }

    p {
      @include normal;
      font-size: 24px;
      line-height: 28px;
      color: #ffffff;
      text-shadow: 0px 0px 4px rgba(0, 0, 0, 0.5);
      margin-bottom: 50px;
    }

    button {
      //@include medium;
      font-size: 18px;
      @include bold;
      //line-height: 21px;
      text-transform: uppercase;
      color: #623f99;
      background: #d5dd25;
      box-shadow: 0px 2px 12px rgba(213, 221, 37, 0.25);
      border-radius: 30px;
      width: 296px;
      height: 56px;
      border: none;
      outline: none;
      cursor: pointer;
    }
  }
}

// sponsors
.sponsors {
  background: #f8f2ff;

  &__wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 140px;
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;
  }
}

// about
.about {
  position: relative;
  height: 534px;
  margin: 120px 0;
  //overflow: hidden;
  .fixed__bg {
    position: absolute;
    top: 0;
    left: 0;
    height: 534px;
    width: calc(100vw - 455px);
    background-color: rgba(246, 239, 255, 0.8);
    z-index: -1;
  }

  &__content {
    position: relative;
    width: 1200px;
    height: 100%;
    max-width: 100%;
    margin: 0 auto;
    padding-top: 40px;
    padding-left: 39px;

    h1 {
      @include bold;
      font-size: 40px;
      line-height: 47px;
      text-transform: uppercase;
      color: #623f99;
      padding-bottom: 10px;
      width: 160px;
      border-bottom: 2px solid #623f99;
      margin-bottom: 32px;
    }

    p {
      position: relative;
      @include normal;
      font-size: 18px;
      line-height: 21px;
      color: #131313;
      margin-bottom: 35px;
      max-width: 583px;

      &::after {
        content: url("../assets/img/main/checkbox.png");
        position: absolute;
        top: 2px;
        left: -39px;
      }

      &:last-of-type {
        margin-bottom: 0;
      }

      span {
        color: #623f99;
        font-weight: 700;
      }
    }

    &::before {
      content: url("../assets/img/main/about.png");
      position: absolute;
      right: -100px;
      top: 120px;
    }
  }
}

// products
.products {
  padding-bottom: 120px;

  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-align: center;
    text-transform: uppercase;
    color: #623f99;
  }

  .cus_bord {
    width: 160px;
    border-bottom: 2px solid #623f99;
    margin: 10px auto 60px;
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(3, 387px);
    justify-content: space-between;
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;

    .grid_first {
      background-image: url("../assets/img/main/pr1.png");
    }

    .grid_second {
      background-image: url("../assets/img/main/pr2.png");
      background-repeat: no-repeat;
    }

    .grid_third {
      background-image: url("../assets/img/main/pr3.png");
    }

    &__single {
      background-size: 100% 100%;
      height: 322px;
      background: #ffffff;
      box-shadow: 0px 4px 12px rgba(146, 115, 194, 0.5);
      padding-top: 94px;
      padding-right: 194px;
      text-align: right;
      cursor: pointer;
      background-position-x: 200px;

      h2 {
        //@include medium;
        font-size: 24px;
        line-height: 28px;
        text-transform: uppercase;
        color: #623f99;
      }

      .grid_bord {
        width: 60px;
        border-bottom: 1px solid #623f99;
        margin-top: 10px;
        margin-bottom: 20px;
        margin-left: auto;
      }

      p {
        @include normal;
        font-size: 16px;
        line-height: 19px;
        color: #131313;
      }
    }
  }
}

// features
.feature {
  background-image: url("../assets/img/main/feature-bg.png");
  padding: 120px 0 88px;

  &__text {
    @include normal;
    font-size: 18px;
    color: #ffffff;
    text-align: center;
    margin-bottom: 25px;

    span {
      color: #d5dd25;
      font-weight: 700;
    }
  }

  &__title {
    @include bold;
    font-size: 24px;
    line-height: 30px;
    color: #d5dd25;
    text-align: center;
    width: 715px;
    margin: 0 auto 90px;
  }

  &__items {
    width: 63.4%;
    padding: 70px 0 70px 142px;
    background-color: #E2E787;
    margin-left: auto;
    position: relative;

    &:after {
      content: '';
      background-image: url("../assets/img/main/feature-img.png");
      width: 472px;
      height: 352px;
      position: absolute;
      top: 36px;
      right: 92.88%;
    }
  }

  &__item {
    position: relative;
    @include normal;
    font-size: 18px;
    line-height: 22px;
    color: #131313;

    &:not(:last-child) {
      margin-bottom: 30px;
    }

    &:before {
      content: '';
      background-image: url("../assets/img/main/purple-checkbox.png");
      width: 25px;
      height: 17px;
      position: absolute;
      top: 0;
      left: -32px;
    }
  }
}

//main-features
.main-features {
  padding: 120px;
  background-color: #D0C5E0;

  &__title {
    @include bold;
    font-size: 24px;
    color: #623F99;
    line-height: 30px;
    text-align: center;
    text-transform: uppercase;
    margin-bottom: 40px;
  }

  &__row {
    display: flex;
    width: 1200px;
    margin: 0 auto;
    //align-items: flex-start;
  }

  &__box {
    padding: 30px 20px;
    background: #FFFFFF;
    box-shadow: 0 4px 20px rgba(146, 115, 194, 0.5);
    border-radius: 8px;
    width: 387px;

    &:not(:last-child) {
      margin-right: 20px;
    }

    img {
      display: block;
      margin: 0 auto 20px;
    }

    h5 {
      @include bold;
      font-size: 24px;
      line-height: 30px;
      color: #623f99;
      text-transform: uppercase;
      margin-bottom: 20px;
    }

    p {
      @include normal;
      font-size: 16px;
      line-height: 20px;
      color: #131313;
    }
  }
}

// sup txt
.support_txt {
  background-image: url("../assets/img/main/suptxt.png");
  background-size: 100% 100%;
  padding-top: 60px;
  padding-bottom: 120px;
  //height: 291px;

  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-align: center;
    text-transform: uppercase;
    color: #d5dd25;
  }

  &__bord {
    width: 160px;
    margin: 10px auto 30px;
    border-bottom: 2px solid #d5dd25;
  }

  &__subtitle {
    @include normal;
    font-size: 24px;
    line-height: 28px;
    color: #ffffff;
    max-width: 1200px;
    text-align: center;
    margin: 0 auto 57px;

    span {
      color: #d5dd25;
      font-weight: 700;
    }
  }
}

//representations
.representations {
  text-align: center;
  padding-top: 120px;
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
// advantages
.advantages_wrapper {

}

.advantages {
  display: grid;
  grid-template-columns: repeat(2, 590px);
  grid-row-gap: 20px;
  justify-content: space-between;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;

  &__single {
    display: flex;
    align-items: flex-start;
    justify-content: flex-end;
    height: 250px;
    background: #ffffff;
    box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.5);
    border-radius: 8px;
    padding-right: 20px;
    padding-top: 30px;

    .img_title {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
      width: 255px;

      img {
        margin-bottom: 30px;
      }

      h2 {
        @include bold;
        font-size: 24px;
        line-height: 30px;
        text-align: center;
        text-transform: uppercase;
        color: #623f99;
      }
    }

    p {
      @include normal;
      font-size: 16px;
      line-height: 19px;
      color: #131313;
      max-width: 265px;
      margin-left: 35px;
    }
  }
}

// articles
.articles {
  padding: 120px 0;

  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-align: center;
    text-transform: uppercase;
    color: #623f99;
  }

  .articles_bord {
    margin: 10px auto 60px;
    width: 160px;
    border-bottom: 2px solid #623f99;
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(3, 387px);
    width: 1200px;
    max-width: 100%;
    justify-content: space-between;
    margin: 0 auto;
  }
}

.single_item {
  &__date {
    @include normal;
    font-size: 16px;
    line-height: 19px;
    color: #acacac;
    margin-top: 10px;
    margin-bottom: 20px;
  }

  &__title {
    //@include medium;
    font-size: 24px;
    line-height: 28px;
    margin-bottom: 10px;
    color: #623f99;
  }

  &__descr {
    @include normal;
    font-size: 16px;
    line-height: 20px;
    color: rgba(19, 19, 19, 0.8);
  }

  &__more {
    display: inline-block;
    position: relative;
    @include normal;
    font-size: 16px;
    line-height: 19px;
    text-transform: uppercase;
    color: rgba(19, 19, 19, 0.5);
    margin-top: 30px;
    cursor: pointer;

    &::before {
      content: url("../assets/img/main/go.png");
      position: absolute;
      right: -26px;
      top: -2px;
    }
  }
}
</style>
