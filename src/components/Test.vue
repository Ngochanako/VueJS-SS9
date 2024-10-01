<template>
    <div>
        <button @click="handleCLick">Click</button>
        <p>Giá trị count:{{ count }}</p>
    </div>
</template>

<script setup>
import { ref } from "vue";

const count=ref(0)
const handleCLick=()=>{
    count.value++  // Tăng giá trị count lên 1
}
</script>

<style>

</style>