<template>
  <header class="header" :class="routeChecker ? '' : 'header--static'">
    <div class="header__container">
      <nuxt-link :to="localePath('/')" tag="svg" class="header__logo" width="134" height="60">
        <use href="../assets/img/icons.svg#logo"></use>
      </nuxt-link>

      <div class="header__burger" @click="toggleSideBar">
        <svg width="32" height="32">
          <use href="../assets/img/icons.svg#burger"></use>
        </svg>
      </div>

      <div class="header__languages lang-switcher">
        <div class="lang-switcher__lang-box"
             @click="$i18n.locale = 'ru'"
             :class="$i18n.locale === 'ru' ? 'lang-switcher__lang-box--active' : ''">
          RU
        </div>

        <div class="lang-switcher__lang-box"
             @click="$i18n.locale = 'kz'"
             :class="$i18n.locale === 'kz' ? 'lang-switcher__lang-box--active' : ''">
          KZ
        </div>

        <div class="lang-switcher__lang-box"
             @click="$i18n.locale = 'en'"
             :class="$i18n.locale === 'en' ? 'lang-switcher__lang-box--active' : ''">
          ENG
        </div>
      </div>

    </div>

    <div class="side-bar" :class="sideBarOpen === true ? 'side-bar--active' : ''">
      <svg class="side-bar__logo" width="133" height="60">
        <use href="../assets/img/icons.svg#logo-3"></use>
      </svg>

      <svg class="side-bar__close" width="14" height="17" @click="toggleSideBar">
        <use href="../assets/img/icons.svg#close"></use>
      </svg>

      <div class="side-bar__links">
        <div class="side-bar__link" @click.passive="toggleSideBar">
          <nuxt-link :to="localePath('/')" tag="a" exact class="side-bar__link">{{ $t('navigation.main') }}</nuxt-link>
        </div>
<!--        <div class="side-bar__link" @click.passive="toggleSideBar">-->
<!--          <nuxt-link :to="localePath('/Rules')" tag="a" class="side-bar__link">{{ $t('navigation.rules') }}</nuxt-link>-->
<!--        </div>-->
<!--        <div class="side-bar__link" @click.passive="toggleSideBar">-->
<!--          <nuxt-link :to="localePath('/Prizes')" tag="a" href="#" class="side-bar__link">{{ $t('navigation.listOfGoods') }}</nuxt-link>-->
<!--        </div>-->
        <div class="side-bar__link" @click.passive="toggleSideBar">
          <nuxt-link :to="localePath('/Buyers')" tag="a" class="side-bar__link">{{ $t('navigation.customers') }}</nuxt-link>
        </div>
        <div class="side-bar__link" @click.passive="toggleSideBar">
          <nuxt-link :to="localePath('/FAQ')" tag="a" class="side-bar__link">{{ $t('navigation.faq') }}</nuxt-link>
        </div>
        <div class="side-bar__link" @click.passive="toggleSideBar">
          <nuxt-link :to="localePath('/Partnership')" tag="a" class="side-bar__link">{{ $t('navigation.affiliateProgramme') }}</nuxt-link>
        </div>
        <div class="side-bar__link" @click.passive="toggleSideBar">
          <a class="side-bar__link" v-scroll-to="{el:'#footer', duration: 700,}">{{ $t('navigation.contacts') }}</a>
        </div>
        <div class="side-bar__link" @click.passive="toggleSideBar">
          <a href="#" class="side-bar__link" @click="openModal">{{ $t('navigation.support') }}</a>
        </div>
      </div>

      <div class="side-bar__languages lang-switcher lang-switcher--dark">
        <div class="lang-switcher__lang-box"
             @click="$i18n.locale = 'ru'"
             :class="$i18n.locale === 'ru' ? 'lang-switcher__lang-box--active' : ''">
          RU
        </div>

        <div class="lang-switcher__lang-box"
             @click="$i18n.locale = 'kz'"
             :class="$i18n.locale === 'kz' ? 'lang-switcher__lang-box--active' : ''">
          KZ
        </div>

        <div class="lang-switcher__lang-box"
             @click="$i18n.locale = 'en'"
             :class="$i18n.locale === 'en' ? 'lang-switcher__lang-box--active' : ''">
          ENG
        </div>
      </div>

    </div>

    <contact-modal v-if="showModal" @close="showModal = false"></contact-modal>
  </header>

</template>

<script>
import ContactModal from "@/components/ContactModal";

export default {
  components: {
    ContactModal
  },
  data: () => ({
    sideBarOpen: false,
    showModal: false,
  }),
  computed: {
    routeChecker() {
      if(this.$route.path === '/' || this.$route.path === '/kz' || this.$route.path === '/en') {
        return true
      }
    }
  },
  methods: {
    toggleSideBar() {
      this.sideBarOpen = !this.sideBarOpen;
    },
    openModal() {
      this.showModal = true;
    },
  },
  mounted() {

  }
};
</script>

<style lang="scss" scoped>

</style>
