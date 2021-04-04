<template>
  <div class="welcome-section__video-modal video-modal video-modal--open">
    <svg class="video-modal__close" width="23" height="24" @click="$emit('close')">
      <use href="../assets/img/icons.svg#close-2"></use>
    </svg>

    <div class="video-modal__wrapper">
      <video src="../assets/videos/promo-ru.mp4" class="video-modal__video" controls autoplay v-if="$i18n.locale === 'ru'"></video>
      <video src="../assets/videos/promo-kz.mp4" class="video-modal__video" controls autoplay v-if="$i18n.locale === 'kz'"></video>
    </div>
  </div>
</template>

<script>
export default {}
</script>
