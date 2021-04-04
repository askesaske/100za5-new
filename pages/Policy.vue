<template>
  <div class="info-page">
    <img src="../assets/img/rules-left.png" alt="" class="info-page__left">
    <img src="../assets/img/rules-right.png" alt="" class="info-page__right">

    <div class="info-page__container">
      <h3 class="info-page__heading page-title">
        {{ $t('policy.heading') }}
      </h3>

      <div class="info-page__section">
        <p class="info-page__text">
          {{ $t('policy.text1') }}
        </p>
        <p class="info-page__text">
          {{ $t('policy.text2') }}
        </p>
        <p class="info-page__text">
          {{ $t('policy.text3') }}
        </p>
      </div>

      <div class="info-page__section">
        <h5 class="info-page__title">
          {{ $t('policy.section1.heading') }}
        </h5>
        <p class="info-page__text">
          {{ $t('policy.section1.title1') }}
          <br>
          {{ $t('policy.section1.text1') }}
          <br>
          {{ $t('policy.section1.text2') }}
          <br>
          {{ $t('policy.section1.text3') }}
          <br>
          {{ $t('policy.section1.text4') }}
        </p>
        <p class="info-page__text">
          {{ $t('policy.section1.title2') }}
        </p>
      </div>

      <div class="info-page__section">
        <h5 class="info-page__title">
          {{ $t('policy.section2.heading') }}
        </h5>
        <p class="info-page__text">
          {{ $t('policy.section2.title1') }}
        </p>
        <p class="info-page__text">
          {{ $t('policy.section2.title2') }}
          <br>
          {{ $t('policy.section2.text1') }}
          <br>
          {{ $t('policy.section2.text2') }}
          <br>
          {{ $t('policy.section2.text3') }}
          <br>
          {{ $t('policy.section2.text4') }}
          <br>
          {{ $t('policy.section2.text5') }}
        </p>
        <p class="info-page__text">
          {{ $t('policy.section2.title3') }}
        </p>
      </div>

      <div class="info-page__section">
        <h5 class="info-page__title">
          {{ $t('policy.section3.heading') }}
        </h5>
        <p class="info-page__text">
          {{ $t('policy.section3.title1') }}
        </p>
        <p class="info-page__text">
          {{ $t('policy.section3.title2') }}
          <br>
          {{ $t('policy.section3.text1') }}
          <br>
          {{ $t('policy.section3.text2') }}
          <br>
          {{ $t('policy.section3.text3') }}
          <br>
          {{ $t('policy.section3.text4') }}
        </p>
      </div>

      <div class="info-page__section">
        <h5 class="info-page__title">
          {{ $t('policy.section4.heading') }}
        </h5>
        <p class="info-page__text">
          {{ $t('policy.section4.title1') }}
        </p>
        <div class="info-page__text">
          {{ $t('policy.section4.title2') }} <br>
          <ul>
            <li>
              &check; {{ $t('policy.section4.text1') }}
            </li>
            <li>
              &check; {{ $t('policy.section4.text2') }}
            </li>
            <li>
              &check; {{ $t('policy.section4.text3') }}
            </li>
            <li>
              &check; {{ $t('policy.section4.text4') }}
            </li>
            <li>
              &check; {{ $t('policy.section4.text5') }}
            </li>
            <li>
              &check; {{ $t('policy.section4.text6') }}
            </li>
          </ul>
        </div>
      </div>

      <div class="info-page__section">
        <h5 class="info-page__title">
          {{ $t('policy.section5.heading') }}
        </h5>
        <p class="info-page__text">
          {{ $t('policy.section5.title1') }}
        </p>
        <p class="info-page__text">
          {{ $t('policy.section5.title2') }}
        </p>
      </div>

      <div class="info-page__section">
        <h5 class="info-page__title">
          {{ $t('policy.section6.heading') }}
        </h5>
        <p class="info-page__text">
          {{ $t('policy.section6.title1') }}
        </p>
        <p class="info-page__text info-page__text--bold">
          {{ $t('policy.section6.title2') }}
        </p>
        <p class="info-page__text">
          {{ $t('policy.section6.title3') }}
        </p>
      </div>
    </div>
  </div>
</template>
