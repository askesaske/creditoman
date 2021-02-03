<template>
  <div class="solo">
    <div class="header_descr">
      <div>
        <div class="country_menu">
          <h1>казахстан</h1>
          <p><img src="../../assets/img/solo/loc.png" />300 терминалов</p>
          <p><img src="../../assets/img/solo/user.png" />120 работников</p>
          <p><img src="../../assets/img/solo/case.png" />5 офисов</p>
          <p>
            <img src="../../assets/img/solo/wallet.png" />5 млн сумма выдачи
            займов
          </p>
        </div>
        <p>
          Казахстан – государство в Центральной Азии, которое раньше входило в
          состав СССР. Оно простирается от Каспийского моря на западе до
          Алтайских гор на востоке, где проходит граница с Китаем и Россией.
          Алма-Ата – самый большой город и важный торговый центр страны. Среди
          достопримечательностей города стоит отметить Вознесенский собор
          Русской православной церкви, построенный при Николае II, и Центральный
          государственный музей Республики Казахстан, тысячи экспонатов которого
          позволяют получить представление об истории государства.
        </p>
      </div>
      <img src="../../assets/img/solo/map.png" />
    </div>
    <div class="solo_body">
      <img src="../../assets/img/solo/1.png" />
      <p>
        Казахстан – государство в Центральной Азии, которое раньше входило в
        состав СССР. Оно простирается от Каспийского моря на западе до Алтайских
        гор на востоке, где проходит граница с Китаем и Россией. Алма-Ата –
        самый большой город и важный торговый центр страны. Среди
        достопримечательностей города стоит отметить Вознесенский собор Русской
        православной церкви, построенный при Николае II, и Центральный
        государственный музей Республики Казахстан, тысячи экспонатов которого
        позволяют получить представление об истории государства.
      </p>
    </div>
    <a href="#" class="see_all">
      смотреть все страны<img src="../../assets/img/solo/go.png" />
    </a>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/style/fonts.scss";
.solo {
  padding-bottom: 120px;
  padding-top: 130px;
}
p {
  @include normal;
  font-size: 16px;
  line-height: 19px;
  color: #131313;
  max-width: 488px;
}
.header_descr {
  display: grid;
  grid-template-columns: 520px 590px;
  justify-content: space-between;
  width: 1200px;
  max-width: 100%;
  margin: 0px auto 60px;
  .country_menu {
    background: #f8f2ff;
    height: 227px;
    width: 100%;
    padding-top: 20px;
    padding-left: 20px;
    margin-bottom: 20px;
    h1 {
      @include medium;
      font-size: 40px;
      line-height: 47px;
      text-transform: uppercase;
      color: #623f99;
      margin-bottom: 20px;
    }
    p {
      display: flex;
      align-items: center;
      margin-bottom: 10px;
      &:last-of-type {
        margin-bottom: 0;
      }
      img {
        margin-right: 10px;
      }
    }
  }
}
.solo_body {
  display: grid;
  grid-template-columns: 590px 488px;
  justify-content: space-between;
  width: 1200px;
  max-width: 100%;
  margin: 0 auto;
  padding-top: 60px;
  padding-bottom: 90px;
  p {
    text-align: right;
  }
}
.see_all {
  @include medium;
  font-size: 24px;
  line-height: 28px;
  text-align: center;
  text-decoration-line: underline;
  text-transform: uppercase;
  color: #623f99;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  img {
    margin-left: 10px;
  }
}
</style>
