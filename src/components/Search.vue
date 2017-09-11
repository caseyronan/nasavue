<template>
  <div class="search">

    <h2 class="title is-2">Search NASA images</h2>

    <form v-on:submit.prevent="getResult(query)">
      <div class="field">
        <input class="input" type="text" v-model="query" placeholder="Enter query...">
      </div>
    </form>

    <div class="results" v-if="results">
      <div v-for="result in results">
        <img v-bind:src="result.links[0].href"/>
      </div>
    </div>

  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'search',
  data () {
    return {
      query: '',
      results: '',
    }
  },
  methods: {
    getResult(query) {
      axios.get('https://images-api.nasa.gov/search?q=' + query + '&media_type=image').then( response => {
        console.log(response.data.collection.items);
        this.results = response.data.collection.items;
      });
    }
  },
}
</script>


<style scoped>
.results img {
  max-width: 50%;
  max-height: 300px;
  margin: 10px;
}

h1, h2 {
  font-weight: normal;
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
