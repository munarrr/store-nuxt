<template>
<div>
   <section class="page-banner">
    <div class="image-layer" style="background-image:url(/images/background/background.jpg);"></div>
    <div class="shape-1"></div>
    <div class="shape-2"></div>
    <div class="banner-inner">
      <div class="auto-container">
        <div class="inner-container clearfix">
        Личный кабинет
        </div>
      </div>
    </div>
  </section>
  <div class="flex">
    <div class="profile-right">
     <p @click="activeLink = 1" :class="[activeLink == 1 ? 'active' : '']">Личные данные</p> 
     <p  @click="activeLink = 2" :class="[activeLink == 1 ? 'active' : '']">Мои адреса</p> 
     <p  @click="activeLink = 3" :class="[activeLink == 1 ? 'active' : '']">История заказов</p> 
    </div>
      <div v-if="activeLink === 1" class="right-col col-xl-4 col-lg-12 col-md-12 col-sm-12">
          <div class="inner">
            <div class="form-box wow fadeInRight" data-wow-delay="0ms" data-wow-duration="1500ms">
              <div class="default-form">
                <h4>Личные данные<span>.</span></h4>
                <form method="post" action="#">
                  <div class="form-group">
                  </div>
                  <div class="form-group">
                    <div class="field-inner">
                      <input type="email" name="email" value="" placeholder="Email Address"
                             required="">
                              <input type="email" name="Имя" value="" placeholder="Email Address"
                             required="">
                              <input type="password" name="Password" value="" placeholder="Email Address"
                             required="">
                              <input type="password" name="Password" value="" placeholder="Email Address"
                             required="">
                    </div>
                  </div>
                  <div class="form-group">
                    <button class="theme-btn btn-style-one">
                      <i class="btn-curve"></i>
                      <span class="btn-title">Отправить</span>
                    </button>
                  </div>
                </form>
              </div>
            </div>
          </div>
      </div>
      <div v-if="activeLink === 2">
      Мои адреса
      </div>
       <div v-if="activeLink === 3">
    
      </div>
  </div>
</div>
</template>

<script>
export default {
  data(){
    return{
      activeLink:1
    }
  }
}
</script>

<style>
.flex{
  display: flex;
}
.profile-right{
  border:1px solid black;
  padding:10px;
  text-align:center;
}
</style>