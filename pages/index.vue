<template>
  <main class="main">

    <section class="main__welcome-section welcome-section">
      <div class="welcome-section__container">
        <div class="welcome-section__info">
          <h1 class="welcome-section__heading">
            {{ $t('welcome.heading') }}
          </h1>

          <p class="welcome-section__text">
            {{ $t('welcome.subtitle') }}
          </p>
          <div class="welcome-section__row welcome-section__row--desktop">
            <button class="welcome-section__btn" v-scroll-to="{el:'#products', duration: 700,}">
              {{ $t('welcome.buttonTxt') }}
            </button>

            <div class="welcome-section__video" @click="openVideo">
              <div class="welcome-section__play-box">
                <svg width="12" height="15">
                  <use href="../assets/img/icons.svg#play"></use>
                </svg>
              </div>

              {{ $t('welcome.videoTxt') }}
            </div>

            <video-modal v-if="videoOpened" @close="videoOpened = false"></video-modal>
          </div>
        </div>

        <div class="welcome-section__slider">
          <div class="swiper-container welcome-section__swiper-container">
            <div class="swiper-wrapper welcome-section__swiper-wrapper">
              <div class="swiper-slide welcome-section__swiper-slide" data-swiper-autoplay="2000">
                <img src="../assets/img/slider-2.png" alt="">
              </div>
              <div class="swiper-slide welcome-section__swiper-slide" data-swiper-autoplay="2000">
                <img src="../assets/img/slider-1.png" alt="">
              </div>
              <div class="swiper-slide welcome-section__swiper-slide" data-swiper-autoplay="2000">
                <img src="../assets/img/slider-3.png" alt="">
              </div>
              <div class="swiper-slide welcome-section__swiper-slide" data-swiper-autoplay="2000">
                <img src="../assets/img/slider-4.png" alt="">
              </div>
            </div>
            <div class="swiper-pagination welcome-section__pagination"></div>
          </div>
        </div>

        <div class="welcome-section__row welcome-section__row--tab">
          <button class="welcome-section__btn" v-scroll-to="{el:'#products', duration: 700,}">
            {{ $t('welcome.buttonTxt') }}
          </button>

          <div class="welcome-section__video" @click="videoOpened = true">
            <div class="welcome-section__play-box">
              <svg width="12" height="15">
                <use href="../assets/img/icons.svg#play"></use>
              </svg>
            </div>

            {{ $t('welcome.videoTxt') }}
          </div>

          <video-modal v-if="videoOpened" @close="videoOpened = false"></video-modal>
        </div>
      </div>
    </section>

    <section class="main__participant participant">
      <div class="participant__container">
        <h2 class="participant__heading heading-medium">
          {{ $t('membership.heading') }}
        </h2>

        <div class="participant__steps">

          <div class="participant__step">
            <img src="../assets/img/participant-num1.png" alt=""
                 class="participant__step-number participant__step-number--01">

            <img src="../assets/img/participant-step1.png" alt="">

            <p class="participant__step-title" v-html="$t('membership.stepTitle1')"></p>
          </div>

          <div class="participant__step">
            <img src="../assets/img/participant-num2.png" alt=""
                 class="participant__step-number participant__step-number--02">

            <img src="../assets/img/participant-step2.png" alt="">

            <p class="participant__step-title" v-html="$t('membership.stepTitle2')"></p>
          </div>

          <div class="participant__step">
            <img src="../assets/img/participant-num3.png" alt=""
                 class="participant__step-number participant__step-number--03">

            <img src="../assets/img/participant-step3.png" alt="">

            <p class="participant__step-title" v-html="$t('membership.stepTitle3')"></p>
          </div>

        </div>

        <div class="participant__qr-box">
          <img src="../assets/img/participant-qr.png" alt="" class="participant__qr-img">

          <div class="participant__info">

            <svg class="participant__qr-arrow" width="191" height="55">
              <use href="../assets/img/icons.svg#qr-arrow"></use>
            </svg>

            <p class="participant__qr-title">
              {{ $t('membership.qrText') }}
            </p>

            <div class="participant__download-box">
              <a href="https://play.google.com/store/apps/details?id=io.bloomzed.app">
                <img src="../assets/img/play-market-link.png" alt="">
              </a>
              <a href="https://apps.apple.com/kz/app/bloomzed/id1519162565">
                <img src="../assets/img/app-store-link.png" alt="">
              </a>
            </div>

          </div>
        </div>

        <div class="participant__mobile-app">

          <div class="participant__download-box">
            <a href="https://play.google.com/store/apps/details?id=io.bloomzed.app">
              <img src="../assets/img/play-market-link.png" alt="">
            </a>
            <a href="https://apps.apple.com/kz/app/bloomzed/id1519162565">
              <img src="../assets/img/app-store-link.png" alt="">
            </a>
          </div>

          <svg class="participant__qr-arrow" width="191" height="55">
            <use href="../assets/img/icons.svg#qr-arrow"></use>
          </svg>

          <p class="participant__qr-title">
            {{ $t('membership.downloadApp') }}
          </p>
        </div>

      </div>

    </section>

    <section class="main__benefit-box benefit-box">
      <div class="benefit-box__container">

        <h2 class="benefit-box__title">
          {{ $t('benefit.heading') }}
        </h2>

        <p class="benefit-box__subtitle" v-html="$t('benefit.subtitle')"></p>

        <div class="benefit-box__items">
          <div class="benefit-box__item">
            <svg class="benefit-box__icon" width="80" height="80">
              <use href="../assets/img/icons.svg#prize"></use>
            </svg>

            <p v-html="$t('benefit.cardTitle1')"></p>
          </div>

          <div class="benefit-box__item">
            <svg class="benefit-box__icon" width="80" height="80">
              <use href="../assets/img/icons.svg#coupon"></use>
            </svg>

            <p v-html="$t('benefit.cardTitle2')"></p>
          </div>

          <div class="benefit-box__item">
            <svg class="benefit-box__icon" width="80" height="80">
              <use href="../assets/img/icons.svg#property"></use>
            </svg>

            <p v-html="$t('benefit.cardTitle3')"></p>
          </div>
        </div>

      </div>
    </section>

    <section class="main__pay-box pay-box">

      <img src="../assets/img/pay-box-left.png" alt="" class="pay-box__side-img">

      <div class="pay-box__container">

        <h3 class="pay-box__heading page-title">
          {{ $t('payFee.heading') }}
        </h3>

        <div class="pay-box__row">

          <div class="pay-box__action-box">

            <div class="pay-box__inputs">

              <div class="pay-box__input-group">
                <label class="pay-box__label">{{ $t('payFee.phoneNumber') }}</label>
                <input type="text" class="pay-box__input" placeholder="+7 (777) 777-77-77" v-model="phoneNumber"
                       id="phoneNumber">
              </div>

              <div class="pay-box__input-group">
                <label class="pay-box__label">{{ $t('payFee.promo') }}</label>
                <input type="text" class="pay-box__input pay-box__input--sm"
                       :placeholder="$t('payFee.promoPlaceHolder')"
                       v-model="promoCode">
                <button class="pay-box__apply-btn" @click="checkPromo"
                        :disabled="promoCode === '' || promoCodeUsed === true">
                  {{ $t('payFee.apply') }}
                </button>
                <p class="pay-box__label pay-box__label--mb0"
                   :class="promoCodeStatus === 1 ? 'pay-box__label--overline' : ''">
                  {{ $t('payFee.cost') }}
                  <span>1000 {{ $t('payFee.tenge') }}</span></p>

                <p class="pay-box__new-price" v-if="this.promoCodeStatus === 1">{{ this.price }}
                  <span>{{ $t('payFee.tenge') }}</span></p>
              </div>

            </div>

            <p class="pay-box__policy-text">{{ $t('payFee.policy1') }}
              <nuxt-link to="/Policy" tag="a">{{ $t('payFee.policy2') }}</nuxt-link>
            </p>

            <button class="pay-box__btn button button--lg" @click="payFee">{{ $t('payFee.pay') }}</button>

          </div>

          <img src="../assets/img/pay-box-card.png" alt="" class="pay-box__img">

        </div>
      </div>

    </section>

    <section class="main__white-section white-section" id="products">
      <img src="../assets/img/white-section-left.png" alt=""
           class="white-section__side-img white-section__side-img--left">
      <img src="../assets/img/white-section-right.png" alt=""
           class="white-section__side-img white-section__side-img--right">

      <div class="white-section__container">

        <div class="white-section__box">

          <h2 class="white-section__heading heading-medium">
            {{ $t('products.heading') }}
          </h2>

          <p class="white-section__subtitle">
            {{ $t('products.subtitle') }}
          </p>

          <div class="white-section__list products-slider">

            <div class="swiper-container products-slider__swiper-container">
              <div class="swiper-wrapper">
                <div v-for="prize in prizes" :key="prize.id" class="swiper-slide products-slider__item">
                  <img :src="require('../assets/img/slider/' + prize.img)" alt="" class="products-slider__img">
                  <div class="products-slider__info">
                    <div class="products-slider__title">
                      {{ prize.name }}
                    </div>
                    <div class="products-slider__desc" v-html="prize.desc">
                    </div>
                  </div>
                </div>
              </div>
              <div class="swiper-pagination products-slider__pagination"></div>
              <!-- Add Arrows -->
              <div class="swiper-button-next products-slider__next"></div>
              <div class="swiper-button-prev products-slider__prev"></div>
            </div>

          </div>

        </div>

        <div class="white-section__box">

          <h2 class="white-section__heading heading-medium">
            {{ $t('customers.heading') }}
          </h2>

          <p class="white-section__subtitle">
            {{ $t('customers.subtitle') }}
          </p>

          <div class="white-section__list customers-list">

            <div class="customers-list__item" v-for="(w, i) in winners" :key="w.id" v-if="i <= 5">
              <img src="../assets/img/person1.png" alt="" class="customers-list__img">
              <p class="customers-list__name">
                {{ w.participant.name }}
              </p>
              <div v-for="d in draws" :key="d.id" v-if="d.id === w.draw.id">
                <p class="customers-list__date">
                  {{ d.date  | moment('DD.MM.YYYY') }}
                </p>
              </div>
            </div>

          </div>

          <nuxt-link to="/Buyers" tag="button" class="white-section__btn button button--md">
            {{ $t('customers.viewAll') }}
          </nuxt-link>

        </div>

      </div>

    </section>

  </main>
</template>

<script>
import Swiper, {Pagination, Autoplay, Navigation} from 'swiper';
import VideoModal from "@/components/VideoModal";
import {uuid} from 'vue-uuid';
import IMask from 'imask';

Swiper.use([Pagination, Autoplay, Navigation]);


export default {
  components: {
    VideoModal
  },
  data() {
    return {
      videoOpened: false,
      draws: [],
      winners: [],
      phoneNumber: '',
      promoCode: '',
      idempotency: '',
      promoCodeStatus: null,
      promoCodeData: [],
      promoMessage: '',
      price: 1000,
      errorMessage1: '',
      errorMessage2: '',
      promoCodeUsed: false,
      tmpData: [],

      prizes: [
        {
          id: 1,
          name: "Кофеварка",
          desc: "Начните свой день с отличного настроения и чашечки кофе с наcыщенным вкуcом приготовленным стильной кофеваркой от BOSCH.",
          img: "coffe-machine.png"
        },
        {
          id: 2,
          name: "Пылесос",
          desc: "Беспроводной ручной пылесос с облегченной конструкцией корпуса. Удобный и компактный для легкой уборки.",
          img: "vaccum.png"
        },
        {
          id: 3,
          name: "Массажер",
          desc: "Перкуссионный массажер  для изолированного массажа мышц. Компактный, мощный, эффективный! Для восстановления всех групп мышц, в том числе до и после физических нагрузок. ",
          img: "massager.png"
        },
      ]
    };
  },
  watch: {},
  methods: {

    checkPromo() {
      this.$axios.get("http://10.1.12.36/api/promocodes/check", {
        params: {
          phone: this.phoneNumber
            .replace(/-/g, '')
            .replace('(', '')
            .replace(')', '')
            .replace('+', ''),
          promocode: this.promoCode,
        },
        credentials: true,
        auth: {
          username: 'admin@randomizer.kz',
          password: 'qwerty123'
        }
      })
        .then((response) => {
          this.promoCodeStatus = response.data.success;
          this.promoCodeData = response.data.data;

          var phone = this.phoneNumber
            .replace(/-/g, '')
            .replace('(', '')
            .replace(')', '')
            .replace('+', '');

          localStorage.setItem("phone", phone);
          localStorage.setItem("promo", this.promoCode);

          if (this.promoCodeStatus === 1) {
            if (this.promoCodeData.promocode.type === 'sum') {
              this.price = this.price - this.promoCodeData.promocode.value;
              console.log(this.promoCodeData.promocode.value);
            }
            if (this.promoCodeData.promocode.type === 'percent') {
              var discount = (this.price * this.promoCodeData.promocode.value) / 100;
              this.price = this.price - discount;
              console.log(this.promoCodeData.promocode.value);
            }
            this.promoCodeUsed = true;
          }
          this.$axios.post("http://10.1.12.36/api/promocodes/deactivate", {
            phone: this.phoneNumber
              .replace(/-/g, '')
              .replace('(', '')
              .replace(')', '')
              .replace('+', ''),
            promocode: this.promoCode
          }, {
            credentials: true,
            auth: {
              username: 'admin@randomizer.kz',
              password: 'qwerty123'
            }
          })
            .then(response => this.tmpData = response.data)
            .catch(error => {
              this.errorMessage = error.message;
              console.log("ERROR!", error.message);
            });
        })
        .catch(error => {
          this.errorMessage = error.message;
          console.log("ERROR!", error.message);
        });
    },

    payFee() {
      this.$axios.post("http://79.142.93.158:3333/payments", {
          "paymentType": 1,
          "amount": {
            "sum": this.price * 100,
            "currency": {
              "code": "KZT",
              "minorUnits": 100
            }
          },
          "description": "оплата участия в 100 за 5",
          "phoneNumber": this.phoneNumber
            .replace(/-/g, '')
            .replace('(', '')
            .replace(')', '')
            .replace('+', ''),
          "options": {
            "callbacks": {
              "successUrl": "http://10.1.12.36:8000/Success/",
              "failureUrl": "http://10.1.12.36:8000/Failure/",
              "backUrl": "http://10.1.12.36:8000/Prizes/"
            },
            "promoCode": this.promoCode
          },
          "createNotExistedUse": false,
          "products": [
            {
              "id": 12345,
              "name": "100 за 5",
              "amount": 100000,
              "count": 1,
            }
          ],
          "language": "ru"
        },
        {
          credentials: true,
          auth: {
            username: '8269073975',
            password: '6G@%M{6X%8@DQL%'
          },
          headers: {
            "X-Idempotency": this.idempotency,
          }
        })
        .then(response => {
          window.location.href = response.data.paymentPageUrl;
        })
        .catch(error => {
          this.errorMessage = error.message;
          console.log("ERROR!", error.message);
        });
    },

    openVideo() {
      this.videoOpened = true;
    }
  },
  mounted() {
    var inputMask = document.getElementById('phoneNumber');
    var maskOptions = {
      mask: '+{7}(000)000-00-00'
    };
    var mask = IMask(inputMask, maskOptions);
    mask.updateValue();

    var swiper = new Swiper('.welcome-section__swiper-container', {
      autoplay: {
        delay: 2000
      },
      spaceBetween: 40,
      slidesPerView: 1,
      pagination: {
        el: '.welcome-section__pagination',
      },

      loop: true
    });

    var swiper2 = new Swiper('.products-slider__swiper-container', {
      slidesPerView: 2,
      spaceBetween: 8,
      navigation: {
        nextEl: '.products-slider__next',
        prevEl: '.products-slider__prev',
      },
      pagination: {
        el: '.products-slider__pagination',
      },
      breakpoints: {
        768: {
          slidesPerView: 3,
          spaceBetween: 20,
        },
        1200: {
          slidesPerView: 3,
          spaceBetween: 40,
        }
      }
    });


    this.$axios.get("http://10.1.12.36/api/draws", {
      credentials: true,
      auth: {
        username: 'admin@randomizer.kz',
        password: 'qwerty123'
      }
    })
      .then((response) => {
        for (var i = 0; i <= response.data.data.length; i++) {
          if (response.data.data[i].status !== 1) {
            this.draws.push(response.data.data[i]);
          }
        }
      });

    this.$axios.get("http://10.1.12.36/api/winners", {
      credentials: true,
      auth: {
        username: 'admin@randomizer.kz',
        password: 'qwerty123'
      }
    })
      .then(response => (this.winners = response.data.data));

    this.idempotency = uuid.v4();
  }
};
</script>

<style lang="scss">

</style>
