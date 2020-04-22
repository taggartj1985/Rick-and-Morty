<template lang="html">
<div >
  <h1>Rick And Morty</h1>
  <!-- <div>
    <character-list :characters='characters'></character-list>
    <character-detail v-if="selectedCharacter" :character="selectedCharacter"></character-detail>
  </div> -->
  <label for="character-select">Select A Character</label>
  <select id="character-select" v-model="selectedCharacter">
    <option disabled value="">Select A Character</option>
    <option v-for="character in characters" :value="character">{{character.name}}</option>
  </select>
</div>
</template>

<script>
import CharacterList from './components/CharacterList.vue';
import {eventBus} from './main.js';
import  CharacterDetail from './components/CharacterDetail.vue';

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

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character;
    })

  },
  components: {
    "character-list": CharacterList,
    "character-detail": CharacterDetail
  }
}
</script>

<style lang="css" scoped>
</style>
