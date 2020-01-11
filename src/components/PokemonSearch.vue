<template>
  <div class="pokemonSearch">
    <div class="container">
      <form>
        <div class="form-group">
          <label for="searchPokemon">Rechercher pokemon</label>
          <input
            type="text"
            placeholder="Rechercher pokemon..."
            class="form-control"
            id="searchPokemon"
            aria-describedby="pokemonHelp"
            v-model="searchPokemon"
          />
          <small id="pokemonHelp" class="form-text text-muted">Chercher votre pokemon préférés.</small>
        </div>

        <h2>{{ pokemon.name }}</h2>

        {{ pokemon }}

        <button type="button" v-on:click="searchDitto()" class="btn btn-primary">Submit</button>
      </form>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'PokemonSearch',
  props: {
    msg: String
  },
  data() {
    return {
      searchPokemon: null,
      pokemon: {}
    };
  },
  methods: {
    searchDitto() {
      axios.get('https://pokeapi.co/api/v2/pokemon/' + this.searchPokemon).then(response => {
        this.pokemon = response.data;
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
