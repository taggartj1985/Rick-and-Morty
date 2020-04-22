<template lang="html">
<div >
  <h1>Rick And Morty</h1>
  <div>
    <character-list :characters='characters'></character-list>
    <!-- <list-item v-for="(character, index) in characters" :character="character" :key="index"></list-item> -->
  </div>
</div>
</template>

<script>
import CharacterList from './components/CharacterList.vue';

export default {
  name: 'app',
  data(){
    return {
      characters: [],
      selectedCharacter: null
    };
  },
  mounted(){
    fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(data => this.characters = data.results)
  },
  components: {
    "character-list": CharacterList
  }
}
</script>

<style lang="css" scoped>
</style>
