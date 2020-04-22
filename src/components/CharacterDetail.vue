<template lang="html">
  <div>
   <h3>{{character.name}}</h3>
   <p>status: {{character.status}}</p>
   <p>species: {{character.species}}</p>
 </div>
</template>

<script>
export default {
  name: 'character-detail',
  props: ['character']
}
</script>

<style lang="css" scoped>
</style>
