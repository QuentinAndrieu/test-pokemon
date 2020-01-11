<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/pokemon.jpg" width="600" height="400" />
    <PokemonSearch msg="Welcome to Your Pokemon App" />
  </div>
</template>

<script>
import PokemonSearch from './components/PokemonSearch.vue';

export default {
  name: 'app',
  components: {
    PokemonSearch
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
