<template lang="html">

  <div>
    <select v-on:change="handleSelect" v-model="firstCountry">
        <option v-for="(country, index) in countries" :value="country" key="index">{{country.name}}</option>
      </select>
  </div>

</template>

<script>
export default {
  name: 'first-country',
  props: ['countries'],
  methods: {
    handleSelect(){
      eventBus$emit('first-country-selected', this.firstCountry)
    }
  }
}

</script>

<style lang="css" scoped>
</style>
