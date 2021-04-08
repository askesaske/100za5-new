<template>
  <div class="status-page">
    <div class="status-page__container">
      <img src="../assets/img/success.png" alt="" class="status-page__img">
      <div class="status-page__text">
        Поздравляю, <br>
        Вы стали участником 100za5!
      </div>
      <nuxt-link to="/" tag="button" class="status-page__button button">Вернуться на главную</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tmpData: [],
      errorMessage: '',
      draws: []
    };
  },

  mounted() {
    var phone = localStorage.getItem('phone') || '';
    var code = localStorage.getItem('promo') || '';

    if(code !== '' && phone !== '') {
      localStorage.setItem("phone", '');
      localStorage.setItem("promo", '');
      this.$axios.post("http://10.1.12.36/api/promocodes/deactivate", {
        phone: phone,
        promocode: code
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
    }

    if(code !== '' && phone === '') {
      localStorage.setItem("phone", '');
      localStorage.setItem("promo", '');
      this.$axios.post("http://10.1.12.36/api/promocodes/deactivate", {
        phone: '',
        promocode: code
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
    }

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

<style lang="scss" scoped>
.active_link {
  color: #ffffff;
  text-decoration: none;
}
</style>
