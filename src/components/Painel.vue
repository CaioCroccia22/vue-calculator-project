<script setup>
//Criando um v-model do filho
import { ref } from 'vue';

const selectedOperator = ref(null)

// Cria bindo direto com o v-model que vem com o pai
    const numbersModel = defineModel('numbers')
    const firstInput = defineModel('firstInput')
    const secondInput = defineModel('secondInput')
    const showResult = defineModel('result')
    const emit = defineEmits(['setFocusInput', 'startCalc'])
   

        // @change="emit('getOperator', $event.target.value)"
    const startCalc = () => {
        emit('startCalc', selectedOperator.value)
    }
</script>

<template>
    <div class="container mt-5 p-4">
        <div class="row py-1 rounded">
            <div class="col-md-2 px-4">
                <input type="text" 
                    @focus="emit('setFocusInput','first')"  
                    v-model="firstInput"
                    class="form-control" 
                    placeholder="digite o valor">
            </div>
            <div class="col-md-2">
                <select class="form-select" 
                v-model="selectedOperator"
                id="floatingSelect" aria-label="Floating label select example">
                    <option selected>Selecione a operação</option>
                    <option value="1">Soma</option>
                    <option value="2">Subtração</option>
                    <option value="3">Divisão</option>
                    <option value="4">Multiplicação</option>
                </select>
            </div>
            <div class="col-md-2 px-4">
                <input type="text"
                    @focus="emit('setFocusInput','second')" 
                    v-model="secondInput" 
                    class="form-control" 
                    placeholder="digite o valor">
            </div>
            <div class="col-md-2 px-4">
                <button id="btn-calc" @click="startCalc" class="btn btn-primary">Calcular</button>
            </div>
            <div class="col-md-2 px-4">
                <p class="d-flex justify-content-center align-items-center m-3"  style="color: aliceblue;">{{ showResult }}</p>
            </div>
        </div>
    </div>



</template>

<style scoped>
    .container{
        width: 100vw;
        margin: auto;
        /* background-color: #30323F;  */
        background-color: black;
    }
    .container.mt-5.p-4{
        /* background-color: #30323F;  */
        /* background-color: black; */
        color: #fff;
        font-size: 32px;
        padding-top: 50px;
        border-radius: 50px;
        
    }
    .row.py-1.rounded{
        align-items: center;
        justify-content: center;
        text-align: center;
        display: flex;
    }
   
    #btn-calc{
        background-color: #FF9601;
    }
    
</style>
