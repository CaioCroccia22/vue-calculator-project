<script setup>
    const emit = defineEmits(['clickKeyboard','reset'])

    const handleClick = (n) => {
        emit('clickKeyboard', n)
        console.log(n)
    }
</script>

<template>
    <div class="container rounded">
        <div class="row d-flex">
            <div class="col-md-6 px-5 col-sm-3">
                <button v-for="n in [1,2,3,4,5,6,7,8,9,0]"
                id="number-button"
                :key="n"
                class="btn m-4 btn-secondary  px-4 py-3 rounded-circle"
                @click="handleClick(n)"
                type="button">{{ n }}</button>
                <button id="btn-ac" @click="emit('reset')" class="btn m-4 btn-secondary  px-4 py-3 rounded-circle">AC</button>
                
            </div>
            
        </div>
    </div>

</template>

<style>
.container{
    background-color: 2D2D2;
    width: 100vw;
    height: 100%;
    display: flex;
    justify-content: center;
    
}
.btn{
    background-color: FF96014;
    color: #fff;
    border: none;
    
}
#btn-ac, #btn-dot{
    background-color: #FF9601;
}

@media (max-width: 576px){
    .container{
    max-width: 100%;
    }
    .col-sm-3{
        width: 90%;
        display: grid;
        grid-template-columns: 2fr 2fr;
        
    }
    #number-button{
        width: 55px;
        height: 55px;
    }

}
</style>