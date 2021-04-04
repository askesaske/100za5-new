<template>
  <div class="buyers">

    <img src="../../../assets/img/buyers-left.png" alt="" class="buyers__left">
    <img src="../../../assets/img/buyers-right.png" alt="" class="buyers__right">

    <div class="buyers__container">
      <h3 class="buyers__heading page-title">
        {{ $t('navigation.drawResult') }}
      </h3>

      <table class="buyers__table" v-for="d in draw">
        <tr>
          <th>Номер телефона</th>
          <th>Статус</th>
        </tr>
        <tr v-for="(w, i) in d.participants" :key="w.id">
          <td class="buyers__data">
            {{ i + 1 }}.
            <span>+{{ w.phone.substr(0, 4) + '*****' + w.phone.substr(9, 2) }}</span>
          </td>
          <td class="buyers__data" v-for="winner in winners" :key="winner.id">
            <span v-if="w.id === winner.participant_id" class="buyers__winner">Выиграл</span>
            <span v-else class="buyers__looser">Проиграл</span>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      winners: [],
      draw: [],
      search: '',
      curId: parseInt(this.$route.params.id)
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
      .then(response => {
        this.winners = response.data.data.filter(w => w.draw_id === this.curId)
      });

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
    // var inputMask = document.getElementById('buyerPhone');
    // var maskOptions = {
    //   mask: '+{7}(000)000-00-00'
    // };
    // var mask = IMask(inputMask, maskOptions);
    // mask.updateValue();
  }
}
</script>
