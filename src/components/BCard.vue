<template>
    <v-container @click="click" class="border-birth">
        <v-row class="text-center">
            <v-col cols="12">
                <v-img
                  :src="require(`../assets/${item.img}.png`)"
                  class="my-3"
                  contain
                  height="300">
                </v-img>
            </v-col>
            <v-col cols="12">
                <span class="family-font title">
                    {{item.title}}
                </span>
            </v-col>
            <v-col cols="12">
                <span class="family-font text">
                    {{text}}
                </span>
            </v-col>

        </v-row>
            
    </v-container>
</template>

<script>
export default {
    name: 'BCard',
    props: {
        item: {
          type: Object
        }
    },
    data: () => ({
      counter: 0
    }),
    computed: {
      text () {
        return this.counter == 0 ? this.item.text : this.item.answer
      }
    },
    methods: {
      click () {
        this.item.answer ? 
          this.counter == 0 ? this.counter += 1 : this.newCard()
          : this.newCard()
      },
      newCard () {
        this.counter = 0
        this.$emit('click')
      }
    }
}
</script>

<style scoped>
.family-font {
  font-family: 'Rubik', sans-serif;
  color: white !important;
}
.title {
  font-weight: 900;
  font-size: 48px !important;
}
.text {
  font-weight: 700;
  font-size: 25px !important;
}
.border-birth {
  margin: 20px;
  padding: 20px;
  border-radius: 152px;
  border: 4px solid white;
  width: 90%;
  height: 93%;

}
</style>