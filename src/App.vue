<script setup>
  import Painel from "./components/Painel.vue";
  import Keyboard from "./components/Keyboard.vue";
  import { ref } from 'vue';

  const numbers = ref('')
  const r = ref('')
  const firstInput = ref('')
  const secondInput = ref('')
  const inputSelecionado = ref(null) // vai guardar o nome do input ativo 

  //Para reset do select
  const selectedOperator = ref(null)

  // Função para pegar o input selecionado
  const setFocusInput = (campo) => {
    inputSelecionado.value = campo;
  }


//Calculo da operação 
const calc = (operator) =>{
  // console.log(typeof(firstInput.value)) 
  // console.log(typeof(secondInput.value))

  const a = parseInt(firstInput.value)
  // console.log(a)
  const b = parseInt(secondInput.value)
  // console.log(b)
  let result = ''

  switch (operator){
    case '1':
      result = a + b
      break
    case '2':
      result = a - b
      break
    case '3':
      result = b !== 0 ? a/b: 'Erro: divisão por zero'
      break
    case '4':
      result = a * b
      break
    case '5':
      operator.value = undefined
    default:
      result = 'Operador Inválida'
  }
  r.value = result
  console.log(r.value)
}
  
    ///Seleciona o valeu do input em focus e recebe um parametro numero do teclado 
const selectInput = (n) => {
    
    

    if (inputSelecionado.value === 'first') {
      firstInput.value += n
      
    } else if (inputSelecionado.value === 'second') {
      secondInput.value += n
      
    }
  }

  const cleanInput = () => {
    firstInput.value = '';
    secondInput.value = '';
    r.value = 0;
    selectedOperator.value = null;
    }
</script>

<template>
      <!-- O input ta dentro de painel, mas o valor é controlado por aqui -->
      <Painel 
        v-model:firstInput="firstInput"
        v-model:secondInput="secondInput"
        v-model:result="r"
        v-model:operator = "selectedOperator"
        @setFocusInput="setFocusInput"
        @startCalc="calc"
        ></Painel>  
        <div>
          <Keyboard 
            @clickKeyboard = "selectInput"
            @reset="cleanInput"
            ></Keyboard>
        </div>
</template>

<style>
  

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html{
  background-color: #2D2D2D;
  border: solid 10px #30323F;
  width: 100vw;
  height: 100vh;
  
}

#app {
  background-color: #2D2D2D;
  
}
  
</style>
