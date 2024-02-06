<script>
import axios from 'axios';
import { store } from './data/store.js';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue';
export default {
  name: 'Pokedex',
  components: { AppMain, AppHeader },
  data() {
    return {
      type: '',
      searchEndpoint: endpoint
    };
  },
  methods: {
    searchCharacters(type) {
      if (type === '') {
        this.searchEndpoint = endpoint;
      } else {
        this.searchEndpoint = `${endpoint}/?eq[type1]=${type}`;
      }
      axios.get(this.searchEndpoint).then(res => {
        store.characters = res.data.docs;
        console.log(this.searchEndpoint);
      });
    },
    handleTypeSelected(type) {
      this.type = type;
      this.searchCharacters(type);
    }
  },
  created() {
    this.handleTypeSelected('');
  }

};
</script>

<template>
  <AppHeader @type-selected="handleTypeSelected" />
  <AppMain />
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>
