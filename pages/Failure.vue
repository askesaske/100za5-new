<template>
  <div class="status-page">
    <div class="status-page__container">
      <img src="../assets/img/failure.png" alt="" class="status-page__img">
      <div class="status-page__text">
        Оплата не прошла, <br>
        попробуйте еще раз
      </div>
      <nuxt-link to="/Prizes" tag="button" class="status-page__button button">Попробовать еще раз</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.active_link {
  color: #ffffff;
  text-decoration: none;
}
</style>
