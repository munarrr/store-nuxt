<template>
  <section class="about-section">
    <div class="auto-container">
      <div class="row clearfix">
        <!--Image Column-->
        <div class="image-column col-xl-6 col-lg-12 col-md-12 col-sm-12">
          <div class="inner">
            <div class="image-block wow fadeInLeft" data-wow-delay="0ms" data-wow-duration="1500ms"><img
              src="/images/background/brand.png" alt=""></div>
          </div>
        </div>
        <!--Text Column-->
        <div class="text-column col-xl-6 col-lg-12 col-md-12 col-sm-12">
          <div class="inner">
            <div class="sec-title">
              <h2>О БРЕНДЕ<span class="dot">.</span></h2>
              <div class="lower-text">M.MANZONI - это немецкий бренд мужской одежды, производящий изделия на территории Италии, Румынии, Турции и Португалии.</div>
            </div>
            </div>
            <div class="link-box">
              <nuxt-link class="theme-btn btn-style-one" to="/about">
                <i class="btn-curve"></i>
                <span class="btn-title">В каталог</span>
              </nuxt-link>
            </div>
          </div>
        </div>
    </div>
     <div class="auto-container2">
      <div class="row clearfix">
        <!--Text Column-->
        <div class="text-column col-xl-6 col-lg-12 col-md-12 col-sm-12">
          <div class="inner2">
            <div class="sec-title2">
              <h2 class="sec-title-text2">СКИДКИ ДО 20-30 %</h2>
              <div class="sec-title-text2-des">НА ВЕСЬ АССОРТИМЕНТ</div>
               <nuxt-link  to="/products">
                <span class="sec-button">В каталог</span>
              </nuxt-link>
            </div>
            </div>
           
          </div>
            <!--Image Column-->
            <div class="image-column col-xl-6 col-lg-12 col-md-12 col-sm-12">
              <div class="about-box-image">
                <div  data-wow-delay="0ms" data-wow-duration="1500ms"><img class="about-box-image-one"
                  src="/images/background/brand.png" alt=""></div>
                   <div  data-wow-delay="0ms" data-wow-duration="1500ms"><img class="about-box-image-two"
                  src="/images/background/brand.png" alt=""></div>                  
              </div>
            </div>
        </div>
    </div>
  </section>
</template>

<script>
    export default {
        name: "About"
    }
</script>

<style scoped>
.about-box-image{
  display: flex;
  align-items: center;
  justify-content: center;

}
.about-box-image-one{
  max-width: 100%;
  width:200px;
  height:300px;
  margin:20px;
}
.about-box-image-two{
  max-width: 100%;
  width:200px;
  height:300px;
  margin:20px;
}
</style>
