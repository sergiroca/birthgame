<template>
  <v-app>
    <v-main>
      <BLanding
        v-if="counter == 0"
        @click="play"/>
      <BCard
        @click="newCard"
        :item="card"
        v-else/>
    </v-main>
  </v-app>
</template>

<script>
import BLanding from './components/BLanding';
import BCard from './components/BCard';

export default {
  name: 'App',

  components: {
    BLanding,
    BCard
  },

  data: () => ({
    counter: 0,
    cards: [
        {
          title: 'Fact or fiction',
          text: 'You tell your baby about yourself every moment. Even if you dont talk to her/him',
          answer: 'With thoughts and feelings you trigger physical changes in you - and also in your baby.',
          bool: true,
          img: 'tree'
        },
        {
          title: 'Fact or fiction',
          text: 'The development of your unborn child follows only a genetic plan',
          answer: 'Not only, the development is much more influenced by external conditions.',
          bool: false,
          img: 'babybuda'
        }
      ]
  }),
  computed: {
    card () {
      return this.cards[this.counter - 1]
    },
  },
  methods: {
    play () {
      this.counter += 1
    },
    newCard () {
      this.counter < this.cards.length ? this.counter += 1 : this.counter = 0
    }
  }
};
</script>

<style scoped>
  /deep/ .v-main__wrap {
    background-color: black !important;
  }
  /deep/ .v-app-bar {
    background-color: black !important;
  }
</style>
