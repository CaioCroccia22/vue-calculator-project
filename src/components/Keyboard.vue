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
            <div class="col-6 px-5">
                <button v-for="n in [1,2,3,4,5,6,7,8,9,0]"
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
</style>