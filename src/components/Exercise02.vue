<template>
    <div>
        <input type="color" v-model="typeColor">
        <p>Mã Màu:{{ typeColor }}</p>
    </div>
</template>

<script setup>
import { ref } from "vue";

const typeColor=ref('')
</script>

<style>

</style>