<template lang="html">

  <div>
    <select v-on:change="handleSelect" v-model="secondCountry">
        <option v-for="(country, index) in countries" :value="country" >{{country.name}}</option>
      </select>
  </div>

</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: 'second-country',
  props: ['countries'],
  data(){
    return {
      secondCountry: {}
    }
  },
  methods: {
    handleSelect(){
      eventBus.$emit ('second-selected-country', this.secondCountry)
    }
  }
}

</script>

<style lang="css" scoped>
</style>
