<template>
    <div>
        <form @submit.prevent="login">
            <h2>Đăng nhập</h2>
            <p>Email</p>
            <input type="text" required v-model="user.email">
            <p>Mật khẩu</p>
            <input type="password" required v-model="user.password">
            <br>
            <button type="submit">Đăng nhập</button>
            <div v-if="notifyLogin">Đăng nhập thành công</div>
            <div v-if="notifyError">Thông tin đăng nhập chưa chính xác</div>
        </form>
    </div>
</template>

<script setup>
import { reactive, ref } from "vue";
const list=reactive(JSON.parse(localStorage.getItem('users'))||[]);
 const user=reactive({
    email:'',
    password:'',
 }) 
const notifyLogin=ref(false);
const notifyError=ref(false);
const login=()=>{
    const userFound=list.find(item=>item.email===user.email&&item.password===user.password);
    if(userFound){
        localStorage.setItem('user',JSON.stringify(userFound));
        notifyLogin.value=true;
    }else{
        notifyError.value=true;
    }
 
}  
</script>

<style scoped>
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