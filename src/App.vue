<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-
import 'normalize.css';
import HelloWorld from './components/HelloWorld.vue';
import Card from './components/Card.vue';
import Scoreboard from './components/Scoreboard.vue';
import TrumpTracker from './components/TrumpTracker.vue';
import PageHeader from './components/Header.vue';
import Info from './components/Info.vue';

import { reactive } from 'vue';

let state = reactive({
  showInfo: false,
});

const toggleInfo = function() {
  state.showInfo = !state.showInfo;
  console.log(state.showInfo);
}
</script>

<template>
  <PageHeader @show-info="toggleInfo"/>
  <TrumpTracker />
  <Info v-if="state.showInfo" @close-info="toggleInfo"/>
  <Scoreboard />
  <Card suit="club" value="5" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
