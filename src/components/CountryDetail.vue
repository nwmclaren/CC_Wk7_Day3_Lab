<template lang="html">
  <div v-if='country'>
    <h3> {{country.name}}</h3>
    <h3> {{country.capital}}</h3>
  </div>

</template>

<script>
export default {
  name: "country-detail",
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
