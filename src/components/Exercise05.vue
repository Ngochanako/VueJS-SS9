<template>
   <div>
       <p>Giới tính:{{ selectedOption }}</p>
       <form >
        <label>
            <input
          type="radio"
          value="Nam"
          v-model="selectedOption"
           />
          Nam
      </label>
      <label>
            <input
          type="radio"
          value="Nữ"
          v-model="selectedOption"
           />
          Nữ
      </label>
      <label>
            <input
          type="radio"
          value="Khác"
          v-model="selectedOption"
           />
          Khác
      </label>
       </form>
   </div>
</template>

<script setup>
import { ref } from "vue";

const selectedOption=ref('')
</script>

<style>

</style>