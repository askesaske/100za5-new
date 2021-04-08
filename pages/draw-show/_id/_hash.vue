<template>
  <div class="prize-page">

    <img src="../../../assets/img/prize-side-left.png" alt="" class="prize-page__left-img">
    <img src="../../../assets/img/100za5-text.png" alt="" class="prize-page__bottom-img">

    <div class="prize-page__container not-found" v-for="d in draw"
         v-if="new Date(d.date.split(' ')[0].split('.').reverse().join('/') + ' ' + d.date.split(' ')[1]) - curDate < 0">
      <img src="../../../assets/img/not-found.png" alt="" class="not-found__img">
      <div class="not-found__text">
        Розыгрыш завершен
      </div>
      <nuxt-link tag="button" :to="'/Results/Draw/' + d.id" class="not-found__btn button">
        Посмотреть результаты розыгрыша
      </nuxt-link>
    </div>

    <div class="prize-page__container" v-for="d in draw" v-else>

      <h3 class="prize-page__heading page-title">
        Подтверждение участия
      </h3>

      <div style="padding:50.25% 0 0 0;position:relative;" class="prize-page__video" v-if="d.prize.videos">
        <iframe :src="'https://www.youtube.com/embed/' + video.split('/')[3] + '?autoplay=1'"
                style="position:absolute;top:0;left:0;width:100%;height:100%;"
                frameborder="0" allow="autoplay; fullscreen; picture-in-picture"
                allowfullscreen
                v-for="video in d.prize.videos">
        </iframe>

<!--        <no-ssr>-->
<!--          <section>-->
<!--            <h2>listening events</h2>-->
<!--            <youtube :video-id="videoId" @ready="ready" @playing="playing"></youtube>-->
<!--          </section>-->
<!--          <section>-->
<!--            <h2>add options</h2>-->
<!--            <youtube :video-id="videoId" player-width="1280" player-height="750" :player-vars="{autoplay: autoState}"></youtube>-->
<!--          </section>-->
<!--        </no-ssr>-->
      </div>

      <div v-else>
        <img :src="d.prize.images[0]" alt="" class="prize-page__img">
      </div>
      <script src="https://player.vimeo.com/api/player.js"></script>

      <div class="prize-page__info prize-page__info--mb60">
        <div class="prize-page__date">
          Дата: <span>{{ d.date.split(' ')[0] }}</span>
        </div>
        <div class="prize-page__date">
          Время: <span>{{ d.date.substr(11, 5) }}</span>
        </div>

        <vue-count-down
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

        <p class="prize-page__text">
          {{ d.comment }}
        </p>

        <p class="prize-page__text">
          {{ registerInfo.message }}
        </p>

      </div>

      <button class="prize-page__button button" @click="registerOnDraw(d)">Зарегистрироваться на розыгрыш</button>

    </div>

    <div class="prize-page__container not-found" v-if="draw.length === 0">
      <img src="../../../assets/img/not-found.png" alt="" class="not-found__img">
      <div class="not-found__text">
        Розыгрыш не найден
      </div>
      <nuxt-link tag="button" to="/Prizes" class="not-found__btn button">
        Посмотреть список розыгрышей
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
      registerInfo: [],
      registerStatus: '',
      curHash: this.$route.params.hash,
      curDate: new Date(),
      // autoState: '0',
      // load: false,
      // videoId: 'OUv8z8ETbQw'
    };
  },
  mounted() {

  },
  computed: {

  },
  methods: {
    registerOnDraw(d) {
      this.$axios.post("http://10.1.12.36/api/draw-register", {
          draw_id: d.id,
          hash: this.curHash
        },
        {
          credentials: true,
          auth: {
            username: 'admin@randomizer.kz',
            password: 'qwerty123'
          }
        })
        .then(response => {
          this.registerInfo = response.data;
          // if(response.data.success === 1) {
          //   this.registerStatus = 'success';
          // } else {
          //   this.registerStatus = 'failure';
          // }
        })
        .catch(error => {
          this.errorMessage = error.message;
          console.log("ERROR!", error.message);
        });
    },
    // ready (event) {
    //   this.player = event.target
    // },
    // playing (event) {
    //   // The player is playing a video.
    // },
    // change () {
    //   // when you change the value, the player will also change.
    //   // If you would like to change `playerVars`, please change it before you change `videoId`.
    //   // If `playerVars.autoplay` is 1, `loadVideoById` will be called.
    //   // If `playerVars.autoplay` is 0, `cueVideoById` will be called.
    //   this.videoId = 'K6NyK1o-SFk'
    // },


    // stop () {
    //   this.player.stopVideo()
    // },
    // pause () {
    //   this.player.pauseVideo()
    // }
  },
  created() {
    this.$axios.get("http://10.1.12.36/api/draws", {
      credentials: true,
      auth: {
        username: 'admin@randomizer.kz',
        password: 'qwerty123'
      }
    })
      .then(response => (this.draw = response.data.data.filter(d => d.id === this.curId)));
  },
}
</script>
