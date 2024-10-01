<template>
   <div>
    <p>Tiến độ hoàn thành: {{ range }} %</p>
    <input type="range" v-model="range">
   </div>
</template>

<script setup>
import { ref } from "vue";

const range=ref(10)
</script>

<style>

</style>