<template>
  <div id="trump-tracker">
    <div 
      :class="[state.activeSuit === suit ? 'active' : '', suit]" 
      v-for="suit in suits" 
      v-html="getSuitSymbol(suit)"
      @click="activateSuit(suit)"
    />
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue';

const suits = ['club', 'diamond', 'spade', 'heart'];

const state = reactive({
  activeSuit: '',
})

const getSuitSymbol = function (suit) {
  switch(suit) {
    case 'spade':
      return '&#9824;';
    case 'heart':
      return '&#9829;';
    case 'club':
      return '&#9827;';
    case 'diamond':
      return '&#9830;';
  }
}
const activateSuit = function (suit) {
  state.activeSuit = suit;
}

</script>

<style lang="css" scoped>

#trump-tracker {
  display: flex;
  flex-flow: row nowrap;
  width: 100%;
  justify-content: space-around;
  font-size: 5rem;
}

.heart, .diamond {
  color: red;
}

.active {
  border: 2px solid black;
}

</style>