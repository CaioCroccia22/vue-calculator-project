<script setup>
    const emit = defineEmits(['clickKeyboard'])

    const handleClick = (n) => {
        emit('clickKeyboard', n)
        console.log(n)
    }
</script>

<template>
    <div class="container m-5">
        <div class="row d-flex">
            <div class="col-6 px-5">
                <button v-for="n in [1,2,3,4,5,6,7,8,9,0]"
                :key="n"
                class="btn m-4 btn-secondary  px-4 py-3 rounded-circle"
                @click="handleClick(n)"
                type="button">{{ n }}</button>
            </div>
        </div>
    </div>

</template>

<style>
.container.m-5{
    background-color: #000000;
    width: 100vw;
}
.btn{
    background-color: #333333;
    color: #fff;
}
</style>