<template>
  <div id="app">
    <h1>Compare Countries</h1>
    <first-country :countries="countries"></first-country>
  </div>
</template>

<script>
import FirstCountry from './components/FirstCountry.vue'

export default {
  name: 'app',
  data() {
    return {
      countries: [{}], //array of country objects with VATs included
      firstCountry: null, //Object of country that has been selected
      secondCountry: null,
      CompletedTrip: [] //object of the beer when it's been selected as favourite
    }
  },

  mounted(){
    fetch('http://api.worldbank.org/v2/country?format=json')
      .then(response => response.json())
      .then(countries => this.countries = countries[1])

      eventBus.$on('first-selected-country', (country) => {
      this.firstCountry = country
  })
},


  components: {
    'first-country': FirstCountry
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
