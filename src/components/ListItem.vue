<template lang="html">
<div id="characterDetail">
  <ul>
  <li v-on:click="handleClick">{{character.name}}</li>
  </ul>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'list-item',
  props: ['character'],
  methods: {
    handleClick(){
      eventBus.$emit('character-selected', this.character)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
