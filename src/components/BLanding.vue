<template>
  <v-container>
    <v-row @click="click" class="text-center">
      <v-col cols="12">
        <span class="play">Play</span>
      </v-col>
      <v-col cols="12">
        <v-img
          :src="require('../assets/logobirth.png')"
          class="my-3"
          contain
          height="300"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'BLanding',

    data: () => ({
    }),
    methods: {
      click () {
        this.$emit('click')
      }
    }
  }
</script>

<style scoped>
.play {
  font-size: 72px;
  font-family: 'Rubik', sans-serif;
  color: white !important;
}
</style>
