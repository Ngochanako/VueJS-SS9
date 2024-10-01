<template>
  <div>
    <p>Ngày sinh:{{ dateOfBirth }}</p>
    <input type="date" v-model="dateOfBirth">
  </div>
</template>

<script setup>
import { ref } from "vue";

const dateOfBirth=ref('');
</script>

<style>

</style>