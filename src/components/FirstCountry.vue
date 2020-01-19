<template lang="html">

  <div>
    <select v-on:change="handleSelect" v-model="firstCountry">
        <option v-for="(country, index) in countries" :value="country" >{{country.name}}</option>
      </select>
  </div>

</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: 'first-country',
  props: ['countries'],
  data(){
    return {
      firstCountry: {}
    }
  },
  methods: {
    handleSelect(){
      eventBus.$emit ('first-selected-country', this.firstCountry)
    }
  }
}

</script>

<style lang="css" scoped>
</style>
