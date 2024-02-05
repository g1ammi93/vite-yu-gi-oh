<script>
import axios from 'axios';
import { store } from './data/store.js';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import AppMain from './components/AppMain.vue';
export default {
  name: 'Pokedex',
  components: { AppMain },
  created() {
    axios.get(endpoint).then(res => {
      store.characters = res.data.docs;
    })
  }
};
</script>

<template>
  <AppMain />
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>
