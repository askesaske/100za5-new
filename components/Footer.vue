<template>
  <footer class="footer" id="footer">
    <div class="footer__container">
      <div class="footer__row">
        <nuxt-link :to="localePath('/')" tag="svg" class="footer__logo" width="221" height="101">
          <use href="../assets/img/icons.svg#logo-2"></use>
        </nuxt-link>

        <div class="footer__socials footer__socials--mobile">
          <a href="#" class="footer__social">
            <svg width="41" height="41">
              <use href="../assets/img/icons.svg#inst"></use>
            </svg>
          </a>

          <a href="#" class="footer__social">
            <svg width="41" height="40">
              <use href="../assets/img/icons.svg#wpp"></use>
            </svg>
          </a>
        </div>

        <div class="footer__link-group">

          <div class="footer__links">
            <nuxt-link :to="localePath('/public-offer')" tag="a" class="footer__link">{{ $t('navigation.publicOffer') }}</nuxt-link>
            <nuxt-link :to="localePath('/Policy')" tag="a" class="footer__link">{{ $t('navigation.policy') }}</nuxt-link>
          </div>

          <div class="footer__links">
<!--            <nuxt-link :to="localePath('/Rules')" tag="a" class="footer__link">{{ $t('navigation.rules') }}</nuxt-link>-->
            <nuxt-link :to="localePath('/FAQ')" tag="a" class="footer__link">{{ $t('navigation.faq') }}</nuxt-link>
          </div>

        </div>

        <div class="footer__contacts">
          <a href="tel: +7 (701) 786 99 76" class="footer__contact">
            <svg width="21" height="21">
              <use href="../assets/img/icons.svg#phone"></use>
            </svg>
            +7 (701)-786-99-76
          </a>

          <div class="footer__contact">
            <svg width="20" height="29">
              <use href="../assets/img/icons.svg#map-pin"></use>
            </svg>
            г. Алматы <br>
            ул. Ходжанова 92
          </div>
        </div>
      </div>

      <div class="footer__socials footer__socials--desktop">
        <a href="#" class="footer__social">
          <svg width="41" height="41">
            <use href="../assets/img/icons.svg#inst"></use>
          </svg>
        </a>

        <a href="#" class="footer__social">
          <svg width="41" height="40">
            <use href="../assets/img/icons.svg#wpp"></use>
          </svg>
        </a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "assets/scss/abstracts/mixins";

.active_link {
  @include text-style(1.8rem, 400, rgba(#f2f2f2, .8));
  text-decoration: none;
}
</style>
