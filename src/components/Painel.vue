<script setup>
// Cria bindo direto com o v-model que vem com o pai
    const numbersModel = defineModel('numbers')
    const first = defineModel('first')
    const second = defineModel('second')
    const setFocusInput = defineEmits(['setFocusInput'])
</script>

<template>
    <div>
        <div class="row py-5 rounded"  style="background-color: #30323F;">
            <div class="col-md-2 px-4">
                <input type="text" 
                    @focus="setFocusInput('firstInput')"  
                    v-model="first"
                    class="form-control" 
                    placeholder="digite o valor">
            </div>
            <div class="col-md-2">
                <select class="form-select" id="floatingSelect" aria-label="Floating label select example">
                    <option selected>Selecione a operação</option>
                    <option value="1">Soma</option>
                    <option value="2">Subtração</option>
                    <option value="3">Divisão</option>
                    <option value="4">Multiplicação</option>
                </select>
            </div>
            <div class="col-md-2 px-4">
                <input type="text"
                    @focus="setFocusInput('secondInput')"
                    v-model="second" 
                    class="form-control" 
                    placeholder="digite o valor">
            </div>
            <div class="col-md-2 px-4">
                <button class="btn btn-primary">Calcular</button>
            </div>
            <div class="col-md-2 px-4">
                <p class="d-flex justify-content-center align-items-center"  style="color: aliceblue;">Resultado</p>
            </div>
        </div>
    </div>



</template>

<style scoped>
    .container{
        width: 100vw;
        margin: auto;
    }
    .row-panel{
        background-color: #30323F; 
        color: #fff;
        font-size: 32px;
        padding-top: 50px;
    }
    
</style>
