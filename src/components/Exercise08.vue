<template>
    <div>
        <form @submit.prevent="addUser">
            <h2>Đăng ký</h2>
            <p>Họ và tên</p>
            <input type="text" required v-model="user.name">
            <p>Email</p>
            <input type="text" required v-model="user.email">
            <p>Mật khẩu</p>
            <input type="password" required v-model="user.password">
            <p>Nhập lại mật khẩu</p>
            <input type="password" required v-model="user.repassword">
            <br>
            <button type="submit">Đăng ký</button>
        </form>
    </div>
</template>

<script setup>
import { reactive } from "vue";

 const user=reactive({
    name:'',
    email:'',
    password:'',
    repassword:''
 }) 
const addProduct=()=>{
    console.log(user);  
}  
</script>

<style scoped>
form{
    display: flex;
    flex-direction: column;
    width: 300px;
    text-align: center;
    padding: 20px;
    box-shadow: 0px 0px 10px 5px rgba(0, 0, 0, 0.5);
}
input{
    border-radius: 5px;
    border:1px solid grey;
    padding: 5px;
}
button{
    background-color:rgb(67, 67, 160);
    color: white;
    padding: 5px;
    border-radius: 5px;
    border: transparent;
}
</style>