<template>
    <div>
        <form @submit.prevent="addProduct">
            <h2>Thêm mới sản phẩm</h2>
            <p>Mã sản phẩm</p>
            <input type="text" required v-model="product.code">
            <p>Tên sản phẩm</p>
            <input type="text" required v-model="product.name">
            <p>Giá</p>
            <input type="number" required v-model="product.price">
            <p>Số lượng</p>
            <input type="number" required v-model="product.quantity">
            <br>
            <button type="submit">Thêm mới</button>
        </form>
    </div>
</template>

<script setup>
import { reactive } from "vue";

 const product=reactive({
    code:'',
    name:'',
    price: 0,
    quantity: 0,
 }) 
const addProduct=()=>{
    console.log(product);  
}  
</script>

<style scoped>
form{
    display: flex;
    flex-direction: column;
    width: 300px;
}
input{
    border-radius: 5px;
    border:1px solid grey;
    padding: 5px;
}
button{
    background-color: brown;
    color: white;
    padding: 5px;
    border-radius: 5px;
    border: transparent;
}
</style>