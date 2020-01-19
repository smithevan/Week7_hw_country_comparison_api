<template lang="html">

  <div v-if="firstCountry" id="countryDetail">
    <h2>{{firstCountry.name}}</h2>
    <p><span>Region</span>: {{firstCountry.region.value}}</p>
  </div>

</template>

<script>
export default {
  name: 'first-country-detail',
  props: ['firstCountry']
}
</script>




<style lang="css" scoped>
</style>
