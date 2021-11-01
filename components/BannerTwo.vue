  <template>
  <section class="banner-section banner-two">

    <div class="banner-carousel">
      <no-ssr>
      <carousel :items="1">
      <!-- Slide Item -->
      <div class="slide-item">
        <div class="image-layer" style="background-image: url(/images/background/background.jpg);"></div>
        <div class="auto-container">
          <div class="content-box">
            <div class="content">
              <div class="inner">
                <h1 class="banner-main-title">M.Manzoni COLLECTION FW 21/22</h1>
                <div class="link-box">
                  <nuxt-link class="ho" to="/about">
                    <span class="banner-btn">nouohn</span>
                  </nuxt-link>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Slide Item -->
      <div class="slide-item">
        <div class="image-layer"  style="background-image: url(/images/background/background.jpg);"></div>
        <div class="auto-container">
          <div class="content-box">
            <div class="content">
              <div class="inner">
                <h1>M.Manzoni COLLECTION FW 21/22</h1>
                <div class="link-box">
                  <nuxt-link class="theme-btn btn-style-one" to="/about">
                    <i class="btn-curve"></i>
                    <span class="btn-title">Каталог</span>
                  </nuxt-link>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Slide Item -->
      <div class="slide-item">
        <div class="image-layer"  style="background-image: url(/images/background/background.jpg);"></div>
        <div class="auto-container">
          <div class="content-box">
            <div class="content">
              <div class="inner">
               M.Manzoni COLLECTION FW 21/22
                <div class="link-box">
                  <nuxt-link class="theme-btn btn-style-one" to="/about">
                    <i class="btn-curve"></i>
                    <span class="btn-title">Каталог</span>
                  </nuxt-link>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      </carousel>
      </no-ssr>
    </div>
  </section>
</template>

<script>
    export default {
        name: "BannerTwo"
    }
</script>

<style scoped>
.banner-main-title{
  color:white;
  width:40%;
  font-weight:300;
  line-height:10px;
};
</style>
