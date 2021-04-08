<template>
  <div class="prizes">
    <img src="../../assets/img/white-section-left.png" alt="" class="prizes__left-img">
    <img src="../../assets/img/prize-right-pattern.png" alt="" class="prizes__right-img">
    <div class="prizes__container">
      <h3 class="prizes__title">
        {{ $t('navigation.listOfGoods') }}
      </h3>

      <div class="prizes__list products-list">
        <nuxt-link
          class="products-list__item"
          :to="'/Prizes/' + draw.id"
          tag="div"
          v-for="(draw, i) in draws"
          :key="draw.id"
          v-if="draw.status !== 1">
          <img :src="draw.prize.images" alt="" class="products-list__img">
          <p class="products-list__name">
            {{ draw.prize.title }}
          </p>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      draws: []
    };
  },
  mounted() {
    this.$axios.get("http://10.1.12.36/api/draws",{
      credentials: true,
      auth: {
        username: 'admin@randomizer.kz',
        password: 'qwerty123'
      }
    })
      .then(response => (this.draws = response.data.data));
  }
}
</script>

<style lang="scss">

</style>


