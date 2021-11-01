<template>
 <section class="page-banner">
    <div class="image-layer" style="background-image:url(/images/background/background.jpg);"></div>
    <div class="shape-1"></div>
    <div class="shape-2"></div>
    <div class="banner-inner">
      <div class="auto-container">
        <div class="inner-container clearfix">
         <form @submit.prevent="PostUser" class="login-form">
           <label for="email">Useer</label>
           <input v-model="username" type="text">
            <label for="email">EMAIL</label>
            <input v-model="email" type="text">
            <label for="email">Password</label>
           <input v-model="password" type="password">
            <label for="email">Password</label>
           <input v-model="password2" type="password">
           <nuxt-link to="/newpassword">Забыли пароль</nuxt-link>
            <nuxt-link to="/registr">Регистрация</nuxt-link>
              <!-- <nuxt-link to="/profile"><button>Войти</button></nuxt-link>  -->
              <button type="submit">Отправить</button>
       </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axiosAPI from '../api/axiosAPI.js'
import axios from 'axios'
export default {
  data(){
    return{
      username:'',
      password:'',
      password2:'',
      email:''
    }
  },
  methods:{
   async PostUser(){     
      try {
         const response = await axios.post('http://134.122.74.23/user/register/',{email:this.email, password:this.password,username:this.username,password2:this.password2})  
         return response         
      }catch(e){
            console.log(e)
      }
    console.log('ko')
    console.log(this.username)
      this.username = ""
    this.password = ""

  },
}
}
</script>

<style>
.login-form{
  display: flex;
  flex-direction:column;
  width:600px;
  margin:0 auto;
}
</style>