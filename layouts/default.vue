<template>
  <div>
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>

<style lang="scss">
@import "../assets/style/fonts.scss";
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.active_link,
.exact_active_link {
  @include extbold;
  color: #623f99 !important;
  border-bottom: 4px solid #623f99 !important;
}
</style>
