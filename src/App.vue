<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import AppMain from './components/AppMain.vue'
export default {
  name: 'Pokedex',
  data: () => ({
    characters: []
  }),
  components: { AppMain },
  created() {
    axios.get(endpoint).then(res => {
      this.characters = res.data.docs;
    })
  }
};
</script>

<template>
  <AppMain :characters="characters" />
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>
