<template>
  <div class="agencies">
    <div class="country">
      <h1>Страны Снг</h1>
      <div class="custom_border" />
      <div class="country__descr">
        <img src="../../assets/img/agencies/sng.png" />
        <div class="text">
          <div class="text__single">
            <h2>Казахстан</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>Азербайджан</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>Украина</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>Киргизия</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>Молдова</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
        </div>
      </div>
    </div>
    <div class="country europe">
      <h1>Страны европы</h1>
      <div class="custom_border" />
      <div class="country__descr">
        <div class="text">
          <div class="text__single">
            <h2>Албания</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>Румыния</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>Сербия</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
        </div>
        <img src="../../assets/img/agencies/europe.png" />
      </div>
    </div>
    <div class="country">
      <h1>Страны азии</h1>
      <div class="custom_border" />
      <div class="country__descr">
        <img src="../../assets/img/agencies/asia.png" />
        <div class="text">
          <div class="text__single">
            <h2>Монголия</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>Вьетнам</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>Филиппины</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>Шри-ланка</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
        </div>
      </div>
    </div>
    <div class="country europe">
      <h1>Страны латинской америки</h1>
      <div class="custom_border" />
      <div class="country__descr">
        <div class="text">
          <div class="text__single">
            <h2>Доминика</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>панама</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
          <div class="text__single">
            <h2>гуатемала</h2>
            <p>300 терминалов</p>
            <p>120 работников</p>
            <p>5 офисов</p>
            <p>4млн USD — сумма займов</p>
          </div>
        </div>
        <img src="../../assets/img/agencies/latin.png" />
      </div>
    </div>
    <div class="country">
      <h1>Страны африки</h1>
      <div class="custom_border" />
      <div class="country__descr">
        <img src="../../assets/img/agencies/asia.png" />
        <div class="text__single africa">
          <h2>намибия</h2>
          <p>300 терминалов</p>
          <p>120 работников</p>
          <p>5 офисов</p>
          <p>4млн USD — сумма займов</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/style/fonts.scss";
.agencies {
  padding-top: 130px;
  padding-bottom: 120px;
}
.custom_border {
  width: 160px;
  border-bottom: 2px solid #623f99;
  margin: 0 auto 60px;
}
.europe {
  .country__descr {
    grid-template-columns: 1fr 590px !important;
  }
}
.africa {
  display: flex !important;
  flex-direction: column !important;
  align-items: center !important;
  justify-content: center !important;
}
.country {
  padding-top: 120px;
  h1 {
    //@include medium;
    font-size: 40px;
    line-height: 47px;
    text-transform: uppercase;
    text-align: center;
    color: #623f99;
  }
  &__descr {
    display: grid;
    grid-template-columns: 590px 1fr;
    grid-column-gap: 60px;
    width: 1200px;
    max-width: 100%;
    margin: 0 auto;
  }
}
.text {
  display: grid;
  grid-template-columns: repeat(2, 203px);
  grid-row-gap: 60px;
  width: 100%;
  justify-content: space-between;
  &__single {
    text-align: center;
    h2 {
      //@include medium;
      font-size: 24px;
      line-height: 28px;
      color: #623f99;
      margin-bottom: 8px;
      text-transform: uppercase;
    }
    p {
      @include normal;
      font-size: 16px;
      line-height: 19px;
      color: #131313;
      margin-bottom: 4px;
      &:last-of-type {
        margin-bottom: 0;
      }
    }
  }
}
</style>
