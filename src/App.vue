<script setup>
  import Painel from "./components/Painel.vue";
  import Keyboard from "./components/Keyboard.vue";
</script>

<template>
    <div class="content text-center">
      <Painel></Painel>
      <Keyboard></Keyboard>
    </div>
    
</template>

<style scoped>
  *{
    padding: 0;
    margin: auto;
    box-sizing: border-box;
  }
  .content{
    height: 100vh;
    width: 100%;
    border: solid 10px #1A1A20;
  }
</style>
