<template>
  <div class="team">
    <h2 class="team_title">
      В первую очередь <span><b>CASHSOSWIFTLY</b></span> - это команда
      <span>трудолюбивых людей</span>, которые хорошо знают и верят в то, что
      они делают. Наша команда насчитывает около <span>1000 человек</span>.
      <br />
      <br />
      Мы преодолели множество проблем, которые поначалу казались невозможными, и
      именно это позволило стать теми, кем мы являемся.
    </h2>
    <h1 class="title">Наша команда</h1>
    <div class="cutom_border" />
    <div class="team_members">
      <div class="box">
        <img src="../assets/img/team/1.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/2.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/3.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/4.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/5.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/6.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/7.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/8.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/8.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/1.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/2.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/3.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
      <div class="box">
        <img src="../assets/img/team/4.png" />
        <p class="box__name">
          Марина Попова
        </p>
        <p class="box__position">Региональный директор</p>
        <div class="box__social">
          <img src="../assets/img/team/wp.png" />
          <img src="../assets/img/team/tg.png" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../assets/style/fonts.scss";
.team {
  background: #fbf9ff;
  padding-top: 130px;
  padding-bottom: 60px;
}
.team_title {
  @include normal;
  font-size: 24px;
  line-height: 28px;
  text-align: center;
  color: #131313;
  width: 1200px;
  max-width: 100%;
  margin: 0px auto 120px;
  span {
    color: #623f99;
  }
}
.title {
  //@include medium;
  font-size: 40px;
  line-height: 47px;
  text-align: center;
  text-transform: uppercase;
  color: #623f99;
}
.cutom_border {
  width: 160px;
  margin: 10px auto 60px;
  border-bottom: 2px solid #623f99;
}
.team_members {
  display: grid;
  grid-template-columns: repeat(4, 285px);
  grid-row-gap: 40px;
  width: 1200px;
  max-width: 100%;
  justify-content: space-between;
  margin: 0 auto;
}
.box {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 334px;
  border-radius: 8px;
  transition: 0.2s;
  padding-top: 40px;
  &:hover {
    background: #ffffff;
    box-shadow: 0px 4px 20px rgba(146, 115, 194, 0.2);
  }
  &__name {
    //@include medium;
    font-size: 24px;
    line-height: 28px;
    color: #623f99;
    margin-top: 20px;
    margin-bottom: 8px;
  }
  &__position {
    @include normal;
    font-size: 16px;
    line-height: 19px;
    color: #898989;
    margin-bottom: 20px;
  }
  &__social {
    img {
      cursor: pointer;
      &:first-of-type {
        margin-right: 16px;
      }
    }
  }
}
</style>
