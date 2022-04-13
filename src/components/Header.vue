<template>
  <div id="header">
    <h1 class="title">
      Clabber
    </h1>
    <nav class="links">
      <a @click="$emit('showInfo')">Info</a>
    </nav>
  </div>
</template>

<script setup>

</script>

<style lang="css" scoped>

#header {
  display: flex;
  flex: row nowrap;
  justify-content: space-between;
  align-items: center;
  background-color: yellow;
}

</style>