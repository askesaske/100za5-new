<template>
  <div>
    <Header/>
    <Nuxt/>
    <Footer/>
  </div>
</template>

<style lang="scss">
@import '../node_modules/swiper/swiper-bundle.css';
@import "../assets/scss/style";

@font-face {
  font-family: 'Arial';
  src: url('../assets/fonts/Arial-bold.eot');
  src: local('☺'), url('../assets/fonts/Arial-bold.woff') format('woff'), url('../assets/fonts/Arial-bold.ttf') format('truetype'), url('../assets/fonts/Arial-bold.svg') format('svg');
  font-weight: 700;
  font-style: normal;
}

@font-face {
  font-family: 'Arial';
  src: url('../assets/fonts/Arial-regular.eot');
  src: local('☺'), url('../assets/fonts/Arial-regular.woff') format('woff'), url('../assets/fonts/Arial-regular.ttf') format('truetype'), url('../assets/fonts/Arial-regular.svg') format('svg');
  font-weight: 400;
  font-style: normal;
}
</style>
