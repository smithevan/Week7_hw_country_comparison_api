<template>
  <div id="app">
    <h1>Compare Countries</h1>
    <first-country :countries="countries"></first-country>
    <second-country :countries="countries"></second-country>
    <!-- <first-country-detail :firstCountry="firstCountry"></first-country-detail> -->
  </div>
</template>

<script>

import FirstCountry from './components/FirstCountry.vue'
import SecondCountry from './components/SecondCountry.vue'
// import FirstCountryDetail from './components/SelectedBeerDetails.vue'
import { eventBus } from './main.js'

export default {
  name: 'app',
  data() {
    return {
      countries: [{}], //array of country objects with info included
      firstCountry: null, //Object of first country that has been selected
      secondCountry: null //Object of second country that has been selected
    }
  },

  mounted(){
    fetch('http://api.worldbank.org/v2/country?format=json')
      .then(response => response.json())
      .then(countries => this.countries = countries[1])

      eventBus.$on('first-selected-country', (country) => {
      this.firstCountry = country

      eventBus.$on('second-selected-country', (country) => {
      this.secondCountry = country
    })
  })
},


  components: {
    'first-country': FirstCountry,
    'second-country': SecondCountry
    // 'first-country-detail': FirstCountryDetail
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
