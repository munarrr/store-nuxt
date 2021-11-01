<template>
 <section class="page-banner">
    <div class="image-layer" style="background-image:url(/images/background/background.jpg);"></div>
    <div class="shape-1"></div>
    <div class="shape-2"></div>
    <div class="banner-inner">
      <div class="auto-container">
        <div class="inner-container clearfix">
           <!--Right Column-->
        <div class="registr-form">
          <div class="inner">
            <div class="form-box wow fadeInRight" data-wow-delay="0ms" data-wow-duration="1500ms">
              <div class="default-form">
                <h4>Регистрация<span>.</span></h4>
                <form @submit.prevent="PostUserName" method="post" action="#">
                  <div class="form-group">
                    <div class="field-inner">
                      <input type="email" v-model="email" name="username" value="" placeholder="Your Name"
                             required="">
                    </div>
                  </div>
                  <div class="form-group">
                    <div class="field-inner">
                      <input type="password" v-model="password" name="password" value="" placeholder="Email Address"
                             required="">
                    </div>
                  </div>
              
                  <div class="form-group">
                    <button type="submit" class="theme-btn btn-style-one">
                      <i class="btn-curve"></i>
                      <span class="btn-title">Регистрация</span>
                    </button>
                  </div>
                </form>
              </div>
            </div>
          </div>
        </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
  data(){
    return{
      email:'',
      password:''
    }
  },
methods: {
   async PostUserName(){     
      try {
         const response = await axios.post('http://134.122.74.23/user/login/',{email:this.email, password:this.password})  
         const res =  localStorage.setItem('user',response.data) 
         console.log(response.data)
         
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

</style>