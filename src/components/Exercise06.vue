<template>
    <div>
        <p>Giá trị người dùng đã chọn: {{ list }}</p>
        <form action="">
            <label for="">
                <input value="Đá bóng" type="checkbox" v-model="list"> Đá bóng
            </label>
            <label for="">
                <input value="Cầu lông" type="checkbox" v-model="list"> Cầu lông
            </label>
            <label for="">
                <input value="Bơi lội" type="checkbox" v-model="list"> Bơi lội
            </label>
            <label for="">
                <input value="Code" type="checkbox" v-model="list"> Code
            </label>
        </form>
    </div>
</template>

<script setup>
import { ref } from "vue";

const list=ref([])

</script>

<style>

</style>