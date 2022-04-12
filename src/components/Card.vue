<template>
  <div class="card">
    <div class="corner-display">
      <div class="value">
        {{ value }}
      </div>
      <div class="suit" v-html="suitSymbol">
      </div>
    </div>

    <div class="middle-display">
      {{ value }}
    </div>

    <div class="corner-display">
      <div class="value">
        {{ value }}
      </div>
      <div class="suit" v-html="suitSymbol">
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const props = defineProps({
  suit: String,
  value: String,
})

const suitSymbol = computed(() => {
  switch(props.suit) {
    case 'spade':
      return '&#9824;';
    case 'heart':
      return '&#9829;';
    case 'club':
      return '&#9827;';
    case 'diamond':
      return '&#9827;';
  }
})

</script>

<style lang="css" scoped>

  .card {
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
    border: 1px solid black;
    border-radius: 5px;
    aspect-ratio: 1 / 1.25;
    max-width: 250px;
  }

  .corner-display {
    padding: 5px;
    line-height: .75;
    font-size: 3rem;
  }
  .corner-display:last-child {
    align-self: flex-end;
  }
  .middle-display {
    font-size: 10rem;
    align-self: center;
  }

</style>