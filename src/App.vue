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
    console.log(inputSelecionado.value)
    
  }

  const calc = (operator) =>{
    if (operator === 'adicao'){
      console.log(operator)
    }
    else if (operator === 'subtracao'){
      console.log(operator)
    }
    else if (operator === 'multiplicacao'){
      console.log(operator)
    }
    else if (operator === 'divisao'){
      console.log(operator)
    }
  }

  

  const selectInput = (n) => {
    console.log('Recebi no selectInput:', n);
    console.log('Input Selecionado:', inputSelecionado.value);

    if (inputSelecionado.value === 'first') {
      firstInput.value += n;
      console.log('Valor do firstInput após o clique:', firstInput.value);
    } else if (inputSelecionado.value === 'second') {
      secondInput.value += n;
    }
  }

  const cleanInput = () => numbers.value = '';
</script>

<template>
    <div class="content text-center">
      <!-- O input ta dentro de painel, mas o valor é controlado por aqui -->
      <Painel 
        v-model:firstInput="firstInput"
        v-model:secondInput="secondInput"
        @setFocusInput="setFocusInput"
        ></Painel>
      <Keyboard @clickKeyboard = "selectInput"></Keyboard>
    </div>
    
</template>

<style scoped>
  *{
    padding: 0;
    margin: auto;
    box-sizing: border-box;
  }
  
</style>
