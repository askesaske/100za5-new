<template>
  <div class="public-offer">
    <div class="public-offer__container">
      <h3 class="public-offer__heading page-title">
        {{ $t('offer.heading') }}
      </h3>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section1.heading') }}
        </h5>
        <p class="public-offer__text" v-html="$t('offer.section1.text1')"></p>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section2.heading') }}
        </h5>
        <p class="public-offer__text" v-html="$t('offer.section2.text1')"></p>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section3.heading') }}
        </h5>
        <div class="public-offer__text">
          {{ $t('offer.section3.title1') }}
          <br> <br>
          {{ $t('offer.section3.title2') }}
          <br> <br>
          {{ $t('offer.section3.title3') }}
          <ul>
            <li> &check; {{ $t('offer.section3.text1') }}
            </li>
            <li> &check; {{ $t('offer.section3.text2') }}</li>
            <li> &check; {{ $t('offer.section3.text3') }}</li>
            <li> &check; {{ $t('offer.section3.text4') }}</li>
          </ul>
          <br> <br>
          {{ $t('offer.section3.title4') }}
        </div>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section4.heading') }}
        </h5>
        <div class="public-offer__text" v-html="$t('offer.section4.text1')"></div>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section5.heading') }}
        </h5>
        <div class="public-offer__text" v-html="$t('offer.section5.text1')"></div>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section6.heading') }}
        </h5>
        <div class="public-offer__text" v-html="$t('offer.section6.text1')"></div>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section7.heading') }}
        </h5>
        <div class="public-offer__text">
          {{ $t('offer.section7.title1') }}
          <br> <br>
          {{ $t('offer.section7.title2') }}
          <br> <br>
          {{ $t('offer.section7.title3') }}
          <br> <br>
          {{ $t('offer.section7.title4') }}
          <br> <br>
          {{ $t('offer.section7.title5') }}
          <br> <br>
          {{ $t('offer.section7.title6') }}
          <br> <br>
          {{ $t('offer.section7.title7') }}
          <br> <br>
          {{ $t('offer.section7.title8') }}
          <br> <br>
          {{ $t('offer.section7.title9') }}
          <br> <br>
          {{ $t('offer.section7.title10') }}
          <br>
          <ul>
            <li>{{ $t('offer.section7.text1') }}</li>
            <li>{{ $t('offer.section7.text2') }}</li>
            <li>{{ $t('offer.section7.text3') }}</li>
            <li>{{ $t('offer.section7.text4') }}</li>
          </ul>
          <br> <br>
          {{ $t('offer.section7.title11') }}
        </div>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section8.heading') }}
        </h5>
        <div class="public-offer__text" v-html="$t('offer.section8.text1')"></div>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section9.heading') }}
        </h5>
        <div class="public-offer__text" v-html="$t('offer.section9.text1')"></div>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section10.heading') }}
        </h5>
        <div class="public-offer__text">
          {{ $t('offer.section10.title1') }}
          <br> <br>
          {{ $t('offer.section10.title2') }}
          <br> <br>
          {{ $t('offer.section10.title3') }}
          <br> <br>
          {{ $t('offer.section10.title4') }}
          <br> <br>
          {{ $t('offer.section10.title5') }}
          <br> <br>
          {{ $t('offer.section10.title6') }}
          <br> <br>
          {{ $t('offer.section10.title7') }}
          <ul>
            <li>
              &check; {{ $t('offer.section10.text1') }}
            </li>
            <li>
              &check; {{ $t('offer.section10.text2') }}
            </li>
            <li>
              &check; {{ $t('offer.section10.text3') }}
            </li>
            <li>
              &check; {{ $t('offer.section10.text4') }}
            </li>
            <li>
              &check; {{ $t('offer.section10.text5') }}
            </li>
          </ul>
        </div>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section11.heading') }}
        </h5>
        <div class="public-offer__text" v-html="$t('offer.section11.text1')"></div>
      </div>

      <div class="public-offer__section">
        <h5 class="public-offer__title">
          {{ $t('offer.section12.heading') }}
        </h5>
        <div class="public-offer__text">
          {{ $t('offer.section12.title1') }}
          <br> <br>
          {{ $t('offer.section12.title2') }}
          <br> <br>
          {{ $t('offer.section12.title3') }}
          <ul>
            <li>
              &check; {{ $t('offer.section12.text1') }}
            </li>
            <li>
              &check; {{ $t('offer.section12.text2') }}
            </li>
            <li>
              &check; {{ $t('offer.section12.text3') }}
            </li>
          </ul>
          <br> <br>
          {{ $t('offer.section12.title4') }}
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {}
</script>
