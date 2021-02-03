<template>
  <div class="About">
    <h1 class="About__title">
      От простой идеи к Международной Fintech компании
    </h1>
    <div class="custom_border" />
    <div class="biography">
      <div class="biography__author">
        <img
          class="biography__author__face"
          src="../assets/img/about/face.png"
        />
        <p class="biography__author__name">
          <span>Родостовец В.Н.</span> <br />
          Учредитель, CEO
        </p>
        <div class="description">
          <p>
            Еще 4 года назад, я уже был уверен что будущее не просто за IT
            технологиями, а за теми технологиями, которые позволят ускорить и
            облегчить бизнес- процессы. <br />
            <br />

            Благодаря совместным усилиям с моим партнером Павлом Гребенниковым,
            который является разработчиком нашего запатентованного программного
            обеспечения, была основана компания, которая чуть более чем за 2
            года стала топовым игроком Казахстанского offline и online рынка
            займов.<br />
            <br />

            Успех нашей компании заключается в инновационной автоматизированной
            бизнес-модели полного цикла, уникальном оборудовании и программном
            обеспечении, которые значительно облегчают и ускоряют процесс выдачи
            кредита по сравнению с традиционными методами кредитования.<br />
            <br />

            Модель настолько успешно показала себя в Казахстане, что было
            принято решение об экспансии на зарубежные рынки. Так была создана
            международная группа компаний CASHSOSWIFTLY с торговой маркой
            KREDITOMAT, которая стала альтернативой действующим крупным
            Fintech-компаниям. <br />
            <br />

            Компании, входящие в Группу не только разделяют схожие бизнес-цели,
            видение и ценности, но и бизнес-процессы и нацеленность на развитие
            партнерских отношений. <br />
            <br />

            Мы фокусируемся на свободе действий, предпринимательстве и отличном
            знании местных рынков. К ведению бизнеса мы подходим очень
            ответственно – соблюдая законы и выполняя все необходимые
            обязательства, как перед государством, так и перед нашими партнерами
            и клиентами.<br />
            <br />

            Я убежден, что внедрение высокотехнологичных решений и продуктов в
            реалиях сегодняшнего дня должно стать неотъемлемой составляющей
            бизнес-процессов в любой стране и компании, претендующей на
            лидерство. Именно такая бизнес-модель способна обеспечит
            долгосрочное стабильное развитие в современном мире.<br />
            <br />
          </p>
        </div>
      </div>
    </div>
    <div class="cachsoswiftly">
      <h1>Организационная структура CASHSOSWIFTLY</h1>
      <div class="custom_border" />
      <img
        class="cachsoswiftly__img"
        src="../assets/img/about/swiftly.png"
        ref="counter_div"
      />
    </div>
    <div class="counter">
      <h1>На сегодняшний день CASHSOSWIFTLY это:</h1>
      <div class="counter__grid">
        <div class="counter__grid__single">
          <animate-number
            ref="myOne"
            from="1"
            to="500"
            duration="1000"
            mode="manual"
          ></animate-number>
          <p>терминалов</p>
        </div>
        <div class="counter__grid__single">
          <animate-number
            ref="myTwo"
            from="1"
            to="16"
            duration="1000"
            mode="manual"
          ></animate-number>
          <p>стран</p>
        </div>
        <div class="counter__grid__single">
          <animate-number
            ref="myThree"
            from="1"
            to="1212"
            duration="1000"
            mode="manual"
          ></animate-number>
          <p>
            общая штатная <br />
            численность
          </p>
        </div>
        <div class="counter__grid__single">
          <h2>7 млрд</h2>
          <p>
            USD выданных <br />
            кредитов за год
          </p>
        </div>
      </div>
    </div>
    <div class="video_cont">
      <button>
        Профиль компании<img src="../assets/img/about/drop.png" />
      </button>
      <img src="../assets/img/about/1.png" />
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    triggerCounter: false
  }),
  watch: {
    triggerCounter() {
      this.$refs.myNum.start();
    }
  },
  created() {
    if (process.client) {
      window.addEventListener("scroll", this.handleScroll);
    }
  },
  destroyed() {
    if (process.client) {
      window.removeEventListener("scroll", this.handleScroll);
    }
  },
  methods: {
    handleScroll(event) {
      if (process.client) {
        if (window.scrollY > this.$refs.counter_div.offsetTop + 400) {
          this.triggerCounter = true;

          return;
        }
      }
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
.About {
  padding-top: 130px;
  overflow: hidden;
  &__title {
    @include medium;
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
  height: 726px;
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
      @include medium;
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
    height: 726px;
    background: #f8f2ff;
    top: -50px;
    left: 132px;
    padding-top: 90px;
    padding-left: 173px;
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
        bottom: 0;
        right: 0;
        transform: rotate(180deg);
        z-index: 999;
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
}
.counter {
  background-image: url("../assets/img/about/bg.png");
  background-size: 100% 100%;
  height: 447px;
  padding-top: 90px;
  h1 {
    @include medium;
    font-size: 40px;
    line-height: 47px;
    color: #d5dd25;
    text-align: center;
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
}
</style>
