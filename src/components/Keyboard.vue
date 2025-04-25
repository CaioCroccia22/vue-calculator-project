<script setup>
    const model = defineModel()
</script>

<template>
    <div class="container m-5">
        <div class="row d-flex">
            <div class="col-6">
                <button v-for="n in [1,2,3,4,5,6,7,8,9,0]"
                :key="n"
                class="btn btn-secondary px-4 py-3 rounded-circle"
                @click="model += n"
                type="button">{{ n }}</button>
            </div>
        </div>
    </div>

</template>

<style>

</style>