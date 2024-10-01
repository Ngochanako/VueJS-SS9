<template>
    <div>
        <form @submit.prevent="addUser">
            <h2>Đăng ký tài khoản</h2>
            <p>Tên sinh viên</p>
            <input type="text" required v-model="user.name">
            <p>Email</p>
            <input type="text" required v-model="user.email">
            <div v-if="notifyEmail" class="notify">Email đã đăng ký rồi</div>
            <p>Mật khẩu</p>
            <input type="password" required v-model="user.password">
            <p>Số điện thoại</p>
            <input type="text" required v-model="user.phone">
            <br>
            <button type="submit">Đăng ký</button>
            <div v-if="notifyRegister" class="notify">Đăng ký tài khoản thành công!</div>
        </form>
    </div>
</template>

<script setup>
import { reactive, ref } from "vue";
const list=reactive(JSON.parse(localStorage.getItem("users"))||[]);
const notifyEmail=ref(false);
const notifyRegister=ref(false);
 const user=reactive({
    name:'',
    email:'',
    password:'',
    phone:''
 }) 
const addUser=()=>{
    if(list.some(u=>u.email===user.email)){
        user.email='';
        notifyEmail.value=true;
        setTimeout(() => {
            notifyEmail.value=false;
        }, 2000);
        return;
    }
    list.push(user);
    localStorage.setItem("users", JSON.stringify(list));
    user.name='';
    user.email='';
    user.password='';
    user.phone='';
    notifyRegister.value=true;
    setTimeout(() => {
        notifyRegister.value=false;
    }, 2000);
 
}  
</script>

<style scoped>
.notify{
    color: red;
    font-size: 12px;
    font-weight: bold;
}
form{
    display: flex;
    flex-direction: column;
    width: 300px;
    
    padding: 20px;
    box-shadow: 0px 0px 10px 5px rgba(0, 0, 0, 0.5);
}
h2{
    text-align: center;
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