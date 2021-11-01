<template>
  <header :class="`main-header header-style-one ${sticky ? 'fixed-header' : ''}`">
    <div class="top-header">
      <p class="top-header-text">add</p>
    </div>
    <!-- Header Upper -->
    <div class="header-upper">
      <div class="inner-container clearfix">
        <!--Logo-->
        <div class="logo-box">
          <div class="logo"><a href="/" title="Linoor - Digital Agency Template"><img
            src="/images/logotip.png" id="thm-logo" alt="Linoor - DIgital Agency HTML Template"
            title="Linoor - DIgital Agency Template"></a></div>
        </div>
        <div class="nav-outer clearfix">
          <!--Mobile Navigation Toggler-->
          <div class="mobile-nav-toggler">
            <span @click="mobileToggle = !mobileToggle" class="icon flaticon-menu-2"></span><span class="txt">Menu</span>
          </div>

          <!-- Main Menu -->
          <nav class="main-menu navbar-expand-md navbar-light">
            <div class="collapse navbar-collapse show clearfix">
              <ul class="navigation clearfix">
                <li class="current dropdown"><nuxt-link to="/">{{lo ? 'Главная': 'Home'}}</nuxt-link>
              
                </li>
                <li class="dropdown"><nuxt-link to="/aboutt">О магазине</nuxt-link>
                 
                </li>
                <li class="dropdown"><nuxt-link to="/products">Каталоги</nuxt-link>
                  
                </li>
                <li class="dropdown"><nuxt-link to="/">Доставка</nuxt-link>
                  
                </li>
                <li class="dropdown"><nuxt-link to="/">Новинки</nuxt-link>
                  
                </li>
                <li><nuxt-link to="/contact">Контакты</nuxt-link></li>
              </ul>
            </div>
          </nav>
        </div>

        <div class="other-links clearfix">
          <div class="link-box">
            <div class="call-us">
              <span @click="lang">EN</span>
              <span>RU</span>
                  <div class="icon-box"><nuxt-link to="/login"><span class="flaticon-user-1"></span></nuxt-link></div>
                  <div class="icon-box"><span class="flaticon-search-1"></span></div>
                  <div class="icon-box"><nuxt-link to="/cart"><span class="flaticon-shopping-cart">{{cart.length}}</span></nuxt-link></div>
            </div>
          </div>
        </div>


      </div>
    </div>
    <!--End Header Upper-->

    <nav class="mobile-nav__container">
      <!-- content is loading via js -->

      <div :class="`collapse navbar-collapse ${mobileToggle ? 'show' : ''} clearfix`">
        <ul class="navigation clearfix">
          <li class="dropdown"><a href="#">Главная<div class="dropdown-btn"><span class="fa fa-angle-right"></span></div></a>
          </li>
          <li><nuxt-link to="/about">О магазине</nuxt-link></li>
          <li class="dropdown"><a href="#">Новинки<div class="dropdown-btn"><span class="fa fa-angle-right"></span></div></a>
            
          </li>
          <li class="dropdown"><nuxt-link to="#">Каталоги<div class="dropdown-btn"><span class="fa fa-angle-right"></span></div></nuxt-link>
          </li>
          <li class="dropdown"><nuxt-link to="#">Новые<div class="dropdown-btn"><span class="fa fa-angle-right"></span></div></nuxt-link>
           
          </li>
          <li class="dropdown"><nuxt-link to="#">Доставка<div class="dropdown-btn"><span class="fa fa-angle-right"></span></div></nuxt-link>
          </li>
          <li><nuxt-link to="/contact">Контакты</nuxt-link></li>
        </ul>
      </div>
    </nav>

  </header>
</template>

<script>
import {mapState} from 'vuex'
  export default {
    name: "Nav",
    data(){
      return {
        sticky: false,
        mobileToggle: false
      }
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll);

      const mobileNav = document.querySelector('.mobile-nav__container');
      const dropdownMenu = mobileNav.querySelectorAll('.dropdown');
      
      for (let i = 0; i < dropdownMenu.length; i++) {
          dropdownMenu[i].addEventListener("click", function() {
          this.classList.toggle('open');
          this.classList.toggle('current');
          });
      }


    },
    methods: {
      lang(){
        this.$store.commit('SWITHLANG')
      },
      handleScroll() {
        if (window.scrollY > 70) {
          this.sticky = true
        } else if (window.scrollY < 70) {
          this.sticky = false
        }
      },
    },
     computed: {
        cart(){
            return this.$store.getters.cart
        },
        lo(){
            return this.$store.state.lang
        }
    },
  }
</script>

<style scoped>
.top-header{
  text-align: center;
  background:#85664E;
}
.top-header-text{
  color:black;
  font-weight: 500;

}
</style>
