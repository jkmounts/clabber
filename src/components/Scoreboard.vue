<template>
  <div id="scoreboard">
    <div class="headers">
      <p>Team 1</p>
      <p>Hand</p>
      <p>Team 2</p>
    </div>

    <div class="hand" v-for="hand in state.hands">
      <div class="team-score">
        <input v-model="state.scoreboard[hand - 1][0]" />
      </div>
      <div class="hand-number">
        {{ hand }}
      </div>
      <div class="team-score">
        <input v-model ="state.scoreboard[hand - 1][1]" />
      </div>
    </div>

    <div id="add-hand-button">
      <button @click="addHand">Next Hand</button>
    </div>

    <div class="totals">
      <p>{{ totals[0] }}</p>
      <p>Total</p>
      <p>{{ totals[1] }}</p>
    </div>

  </div>
</template>

<script setup>
import {ref, reactive, computed} from 'vue';

const state = reactive({
  score: 0,
  scoreboard: [[0, 0]],
  hands: 1,
});

const totals = computed(() => {
  return state.scoreboard.reduce((array, round) => {
    array[0] = Number(array[0]) + Number(round[0]);
    array[1] = Number(array[1]) + Number(round[1]);
    return array;
  }, [0, 0])
})


const addHand = function (){
  state.scoreboard.push([ 0, 0 ]);
  state.hands++;
}


</script>

<style lang="css" scoped>

.hand, .headers, .totals {
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
  max-width: 100%;
}

.hand-number {
  padding: 0 20px;
}

.team-score {
  flex: 1;
}

input {
  width: 100%;
}

</style>