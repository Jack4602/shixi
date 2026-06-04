<template>
<div class="login-container">
<h2>用户登录</h2>
<form @submit.prevent="handleLogin">
<div>
<label>用户名：</label>
<input type="text" v-model="username" placeholder="请输入用户名"/>
</div>
<div>
<label>密码：</label>
<input type="password" v-model="password" placeholder="请输入密码"/>
</div>
<button type="submit">登录</button>
</form>
</div>
</template>

<script setup lang="ts">
import{ref}from'vue'
import{useRouter}from'vue-router'
const username=ref('')
const password=ref('')
const router=useRouter()
const handleLogin=()=>{
alert(`您输入的用户名：${username.value}，密码：${password.value}`)
if(username.value.trim()!==''){
router.push('/home')
}else{
alert('用户名不能为空')
}
}
</script>

<style scoped>
.login-container{
width:300px;
margin:100px auto;
padding:20px;
border:1px solid #ccc;
border-radius:8px;
}
div{
margin-bottom:12px;
}
label{
display:inline-block;
width:60px;
}
input{
padding:4px 8px;
}
button{
margin-left:60px;
}
</style>