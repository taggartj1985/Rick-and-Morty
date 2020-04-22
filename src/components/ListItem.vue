<template lang="html">
<div id="characterDetail">
  <ul>
  <li>{{character.name}}</li>
  </ul>
  </div>
</template>

<script>
export default {
  name: 'list-item',
  props: ['character']
}
</script>

<style lang="css" scoped>
</style>
