<template>
  <div id="container">
    <a class="close-button" @click="$emit('closeInfo')">
      Close X
    </a>
    <div class="info-box">
      Info Goes Here
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="css" scoped>
  #container {
    background-color: rgba(0, 0, 0, 0.7);
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    height: 100vh;
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
  }
  .close-button {
    color: orange;
    align-self: flex-end;
    padding: 20px;
    font-size: 2rem;
  }
  .info-box {
    width: 85%;
    background-color: white;
    min-height: 200px;
  }
</style>