<template>
  <div class="prize-page">

    <img src="../../assets/img/prize-side-left.png" alt="" class="prize-page__left-img">
    <img src="../../assets/img/100za5-text.png" alt="" class="prize-page__bottom-img">

    <div class="prize-page__container" v-for="d in draw" v-show="d.id === curId">
      <h3 class="prize-page__heading page-title">
        Подтверждение участия
      </h3>


      <div style="padding:50.25% 0 0 0;position:relative;" class="prize-page__video" v-if="d.prize.videos">
        <iframe :src="'https://www.youtube.com/embed/' + video.split('/')[3]"
                style="position:absolute;top:0;left:0;width:100%;height:100%;"
                frameborder="0" allow="autoplay; fullscreen; picture-in-picture"
                allowfullscreen
                v-for="video in d.prize.videos">
        </iframe>
      </div>

      <div v-else>
        <img :src="link" alt="" class="prize-page__img" v-for="link in d.prize.images">
      </div>
      <script src="https://player.vimeo.com/api/player.js"></script>

      <div class="prize-page__info">
        <div class="prize-page__date">
          Дата: <span>{{ d.date | moment('DD.MM.YYYY') }}</span>
        </div>
        <div class="prize-page__date">
          Время: <span>{{ d.date.substr(11, 5) }}</span>
        </div>

        <vue-count-down
          v-if="new Date(d.date.split(' ')[0].split('.').reverse().join('/') + ' ' + d.date.split(' ')[1]) - curDate > 0"
          :time="Math.abs(new Date(d.date.split(' ')[0].split('.').reverse().join('/') + ' ' + d.date.split(' ')[1]) - curDate)"
          v-slot="{ days, hours, minutes, seconds }"
          class="prize-page__time-left">
          <div class="prize-page__time-item">
            <div class="prize-page__time-box">
              {{ days }}
            </div>
            <div class="prize-page__time-text">Дней</div>
          </div>
          <div class="prize-page__time-item">
            <div class="prize-page__time-box">
              {{ hours }}
            </div>
            <div class="prize-page__time-text">Часов</div>
          </div>
          <div class="prize-page__time-item">
            <div class="prize-page__time-box">
              {{ minutes }}
            </div>
            <div class="prize-page__time-text">Минут</div>
          </div>
          <div class="prize-page__time-item">
            <div class="prize-page__time-box">
              {{ seconds }}
            </div>
            <div class="prize-page__time-text">Секунд</div>
          </div>
        </vue-count-down>

        <div
          v-else
          class="prize-page__time-left">
          <div class="prize-page__time-item">
            <div class="prize-page__time-box">
              0
            </div>
            <div class="prize-page__time-text">Дней</div>
          </div>
          <div class="prize-page__time-item">
            <div class="prize-page__time-box">
              0
            </div>
            <div class="prize-page__time-text">Часов</div>
          </div>
          <div class="prize-page__time-item">
            <div class="prize-page__time-box">
              0
            </div>
            <div class="prize-page__time-text">Минут</div>
          </div>
          <div class="prize-page__time-item">
            <div class="prize-page__time-box">
              0
            </div>
            <div class="prize-page__time-text">Секунд</div>
          </div>
        </div>

        <p class="prize-page__text">
          {{ d.comment }}
        </p>
      </div>

      <nuxt-link to="/Prizes" tag="a" class="prize-page__back-btn">
        <svg width="25" height="16">
          <use href="../../assets/img/icons.svg#arrow"></use>
        </svg>
        страница Товары
      </nuxt-link>

    </div>

  </div>
</template>

<script>
import VueCountDown from '@chenfengyuan/vue-countdown';

export default {
  components: {
    VueCountDown,
  },
  data() {
    return {
      draw: [],
      curId: parseInt(this.$route.params.id),
      tempData: "",
      errorMessage: "",
      phoneNumber: '',
      curDate: new Date(),
    };
  },
  methods: {

  },
  created() {
    this.$axios.get("http://10.1.12.36/api/draws", {
      credentials: true,
      auth: {
        username: 'admin@randomizer.kz',
        password: 'qwerty123'
      }
    })
      .then(response => {
        this.draw = response.data.data.filter(d => d.id === this.curId);
      });
  },
  mounted() {
  },
  updated() {

  }
}
</script>
