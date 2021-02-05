<template>
  <div class="About">
    <h1 class="About__title">
      От простой идеи <br>
      к Международной Fintech компании
    </h1>
    <div class="custom_border"/>
    <div class="biography">
      <div class="biography__author">
        <img
          class="biography__author__face"
          src="../assets/img/about/face.png"
        />
        <p class="biography__author__name">
          <span>Родостовец В.Н.</span> <br/>
          Учредитель, CEO
        </p>
        <div class="description">
          <p>
            Еще 4 года назад, я уже был уверен что будущее не просто за IT технологиями, а за теми технологиями, которые
            позволят ускорить и облегчить бизнес- процессы. <br/>
            <br/>

            Благодаря совместным усилиям с моим партнером Павлом Гребенниковым, который является разработчиком нашего
            запатентованного программного обеспечения, была основана компания, которая чуть более чем за 2 года стала
            топовым игроком Казахстанского offline и online рынка займов.<br/>
            <br/>

            Успех нашей компании заключается в инновационной автоматизированной бизнес-модели полного цикла, уникальном
            оборудовании и программном обеспечении, которые значительно облегчают и ускоряют процесс выдачи кредита по
            сравнению с традиционными методами кредитования.<br/>
            <br/>

            Модель настолько успешно показала себя в Казахстане, что было принято решение об экспансии на зарубежные
            рынки. Так была создана международная группа компаний CASHSOSWIFTLY с торговой маркой KREDITOMAT, которая
            встала в ряд с действующими крупными международными Fintech-компаниями.<br/>
            <br/>

            Компании, входящие в Группу не только разделяют схожие бизнес-цели, видение и ценности, но и бизнес-процессы
            и нацеленность на развитие партнерских отношений.<br/>
            <br/>

            Мы фокусируемся на свободе действий, предпринимательстве и отличном знании местных рынков. К ведению бизнеса
            мы подходим очень ответственно – соблюдая законы и выполняя все необходимые обязательства, как перед
            государством, так и перед нашими партнерами и клиентами.<br/>
            <br/>

            Я убежден, что внедрение высокотехнологичных решений и продуктов в реалиях сегодняшнего дня должно стать
            неотъемлемой составляющей бизнес-процессов в любой стране и компании, претендующей на лидерство. Именно
            такая бизнес-модель способна обеспечить долгосрочное стабильное развитие в современном мире.<br/>
            <br/>
          </p>
        </div>
      </div>
    </div>
    <div class="priorities">
      <h1>Наши ценности</h1>
      <div class="bord_title"/>
      <div class="grid_items">
        <div class="grid_items__single">
          <img src="../assets/img/main/honest.png"/>
          <h2>Честность</h2>
          <div class="bord_card"/>
          <p>
            Мы знаем, что доверие является основополагающим принципом, и чтобы
            нам доверяли, мы должны оставаться компетентными и честными.
          </p>
        </div>
        <div class="grid_items__single">
          <img src="../assets/img/main/clarity.png"/>
          <h2>Прозрачность</h2>
          <div class="bord_card"/>
          <p>
            Мы раскрываем все правила и условия продуктов простым языком на
            нашем веб-сайте и в различных точках обслуживания.
          </p>
        </div>
        <div class="grid_items__single">
          <img src="../assets/img/main/resp.png"/>
          <h2>Подотчетность</h2>
          <div class="bord_card"/>
          <p>
            Мы осознаем, что в конечном итоге мы несем ответственность перед
            нашими клиентами, и мы неуклонно ориентируемся на максимальное
            долгосрочное партнерство и ценности.
          </p>
        </div>
        <div class="grid_items__single">
          <img src="../assets/img/main/coop.png"/>
          <h2>Сотрудничество</h2>
          <div class="bord_card"/>
          <p>
            Мы создаем команды, чтобы генерировать лучшие идеи и действовать как
            ответственные партнеры со всеми нашими клиентами и служить более
            широким интересам общества.
          </p>
        </div>
      </div>
    </div>
    <div class="cachsoswiftly">
      <h1>Наша команда</h1>
      <div class="custom_border"/>
      <div class="cachsoswiftly__text">
        <p class="cachsoswiftly__subtitle">
          CASHSOSWIFTLY в первую очередь — это команда трудолюбивых людей, которые хорошо <br>
          знают и верят в то, что они делают. Наша команда насчитывает около 1000 человек.
        </p>
        <p class="cachsoswiftly__subtitle">
          Мы преодолели множество проблем, которые поначалу казались невозможными, и именно <br>
          это позволило стать теми, кем мы являемся.
        </p>
      </div>
      <img
        class="cachsoswiftly__img"
        src="../assets/img/about/swiftly.png"
        ref="counter_div"
      />
    </div>
    <div class="counter" id="counter">
      <h1>На сегодняшний день CASHSOSWIFTLY это:</h1>

      <div class="counter__grid">
        <div class="counter__grid__single">
          <animate-number :number="terminalCount"></animate-number>
          <p>терминалов</p>
        </div>
        <div class="counter__grid__single">
          <animate-number :number="countryCount"></animate-number>
          <p>стран</p>
        </div>
        <div class="counter__grid__single">
          <animate-number :number="staffCount"></animate-number>
          <p>
            общая штатная <br/>
            численность
          </p>
        </div>
        <div class="counter__grid__single">
          <div>
            <animate-number :number="cashCount"></animate-number>
            <span>млн</span>
          </div>
          <p>
            USD выданных <br/>
            кредитов
          </p>
        </div>
      </div>
    </div>
    <div class="video_cont">
      <button>
        Профиль компании<img src="../assets/img/about/drop.png"/>
      </button>
      <div class="video_cont__wrapper">
        <iframe width="996" height="538" src="https://www.youtube.com/embed/5qap5aO4i9A" frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                allowfullscreen></iframe>
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
      console.log(this.userScroll + " " + this.counterPos);
    },
  },

  mounted() {
    window.addEventListener('scroll', e => this.userScroll = window.scrollY);
    var counterBox = document.getElementById('counter');
    this.counterPos = this.getPosition(counterBox);
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";

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
    }
  }
}

//  priorities
.priorities {
  background-image: url("../assets/img/about/priority-bg.png");
  padding-top: 120px;
  height: 748px;

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
  }
}

.cachsoswiftly {
  background: #f8f2ff;
  padding-top: 60px;
  padding-bottom: 120px;
  text-align: center;

  h1 {
    @include normal;
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
}

.counter {
  background-image: url("../assets/img/about/bg.png");
  background-size: 100% 100%;
  height: 447px;
  padding-top: 90px;

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
}
</style>
