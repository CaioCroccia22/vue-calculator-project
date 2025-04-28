<script setup>
  import Painel from "./components/Painel.vue";
  import Keyboard from "./components/Keyboard.vue";
  import { ref } from 'vue'

  const numbers = ref('')
  const firstInput = ref('')
  const secondInput = ref('')
  const inputSelecionado = ref(null) // vai guardar o nome do input ativo

  const setFocusInput = (campo) => {
    inputSelecionado.value = campo;
    console.log('O input que recebeu foco foi:', campo)
  }

  const selectInput = (n) => 
    {
      if (inputSelecionado.value === 'firstInput') {
        firstInput.value += n
      
      
      } else if(inputSelecionado.value === 'secondInput'){
        secondInput.value += n
      }
  }

  const cleanInput = () => numbers.value = '';
</script>

<template>
    <div class="content text-center">
      <!-- O input ta dentro de painel, mas o valor é controlado por aqui -->
      <Painel 
        v-model:first="firstInput"
        v-model:second="secondInput"
        @setFocusInput="setFocusInput"
        ></Painel>
      <Keyboard @clickKeyboard = 'selectInput'></Keyboard>
    </div>
    
</template>

<style scoped>
  *{
    padding: 0;
    margin: auto;
    box-sizing: border-box;
  }
  
</style>
