<template>
  <transition name="modal">
    <div class="modal__mask">
      <div class="modal__wrapper">
        <div class="modal__container">

          <div class="modal__content">

            <div class="modal__title">
              {{ $t('contactModal.title') }}
            </div>

            <div class="modal__input-group">
              <input type="text" class="modal__input input" :placeholder="$t('contactModal.name')">
              <input type="text" class="modal__input input" placeholder="E-mail">
              <input type="text" class="modal__input input" :placeholder="$t('contactModal.phone')">
              <textarea class="modal__input input input--textarea" :placeholder="$t('contactModal.message')"></textarea>
            </div>

            <button class="modal__button button button--w100">{{ $t('contactModal.send') }}</button>
          </div>

          <button class="modal__close" @click="$emit('close')">
            <svg width="14" height="17">
              <use href="../assets/img/icons.svg#close-3"></use>
            </svg>
          </button>

        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {

    };
  }
};
</script>
