<template>
  <div id="app">
    <div class="section">
      <div class="container">
        <search></search>
      </div>
    </div>
  </div>
</template>

<script>
import Search from './components/Search'

export default {
  name: 'app',
  components: {
    Search
  }
}
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
