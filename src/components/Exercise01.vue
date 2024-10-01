<template>
    <div>
        <input type="text" v-model="value">
        <p>Giá trị:{{ value }}</p>
    </div>
</template>

<script setup>
import { ref } from "vue";

const value=ref('');
</script>

<style>

</style>