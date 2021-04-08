<template>
  <div class="buyers">

    <img src="../assets/img/buyers-left.png" alt="" class="buyers__left">
    <img src="../assets/img/buyers-right.png" alt="" class="buyers__right">

    <div class="buyers__container">
      <h3 class="buyers__heading page-title">
        {{ $t('navigation.customers2') }}
      </h3>

      <!--      <div class="buyers__search-box">-->
      <!--        <svg width="22" height="22">-->
      <!--          <use href="../assets/img/icons.svg#search"></use>-->
      <!--        </svg>-->
      <!--        <input type="text" class="buyers__input" placeholder="Введите вашу фамилию" v-model="search">-->
      <!--      </div>-->

      <table class="buyers__table">
        <tr>
          <th>Номер телефона</th>
          <th>Товар</th>
          <th>Дата</th>
          <th></th>
        </tr>
        <tr v-for="(w, i) in filteredList" :key="w.id">
          <td class="buyers__data">
            {{ i + 1 }}.
            <span>+{{ w.participant.phone.substr(0, 4) + '*****' + w.participant.phone.substr(9, 2) }}</span>
          </td>
          <td class="buyers__data" v-for="d in draws" :key="d.id" v-if="d.id === w.draw.id"> {{ d.prize.title }}</td>
          <td class="buyers__data buyers__data--red" v-for="d in draws" :key="d.id" v-if="d.id === w.draw.id">
            {{ d.date.split(' ')[0] }}
          </td>
          <td class="buyers__data">
            <nuxt-link tag="button" :to="'Results/Draw/' + w.draw_id" class="buyers__btn">
              Подробнее
            </nuxt-link>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import IMask from "imask";

export default {
  data() {
    return {
      winners: [],
      draws: [],
      search: ''
    };
  },
  computed: {
    filteredList() {
      return this.winners.filter(winner => {
        return winner.participant.name.toLowerCase().includes(this.search.toLowerCase())
      })
    }
  },
  methods: {},
  created() {
    this.$axios.get("http://10.1.12.36/api/winners", {
      credentials: true,
      auth: {
        username: 'admin@randomizer.kz',
        password: 'qwerty123'
      }
    })
      .then(response => (this.winners = response.data.data));

    this.$axios.get("http://10.1.12.36/api/draws", {
      credentials: true,
      auth: {
        username: 'admin@randomizer.kz',
        password: 'qwerty123'
      }
    })
      .then(response => (this.draws = response.data.data));
  },
  mounted() {
    // var inputMask = document.getElementById('buyerPhone');
    // var maskOptions = {
    //   mask: '+{7}(000)000-00-00'
    // };
    // var mask = IMask(inputMask, maskOptions);
    // mask.updateValue();
  }
}
</script>
