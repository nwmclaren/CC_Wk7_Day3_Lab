<template>
<div class="main-container">
  <h1>Countries</h1>
  <country-list :countries = "countries"></country-list>

</div>
</template>

<script>
import CountryDetail from './components/CountryDetail.vue';
import CountryList from './components/CountryList.vue';
import { eventBus } from './main.js';

export default {
  name: 'app',
  data(){
    return {
      countries: []

    }
  },
  mounted() {
  fetch('https://restcountries.eu/rest/v2/all')
  .then(res => res.json())
  .then(countries => this.countries = countries)},
  // eventBus.$on
  components: {
    "country-list": CountryList,
    "country-detail": CountryDetail
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
