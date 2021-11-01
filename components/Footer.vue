<template>
  <div>
  <footer class="main-footer">
    <div class="auto-container">
      <!--Widgets Section-->
      <div class="widgets-section">
        <div class="row clearfix">

          <!--Column-->
          <div class="column col-xl-3 col-lg-6 col-md-6 col-sm-12">
            <div class="footer-widget links-widget">
              <div class="widget-content">
                <div class="row clearfix">
                  <div class="col-md-6 col-sm-12">
                    <ul>
                      <li><a href="#">КОНТАКТЫ</a></li>
                      <li><a href="#">ФИЛИАЛЫ</a></li>
                      <li><a href="#">О МАГАЗИНЕ</a></li>
                      <li><a href="#">ДОСТАВКА</a></li>
                    </ul>
                  </div>
                  <div class="col-md-6 col-sm-12">
                    <ul>
                      <li><a href="#">Аксессуары</a></li>
                      <li><a href="#">Джинсы и брюки</a></li>
                      <li><a href="#">Рубашки</a></li>
                      <li><a href="#">Пальто</a></li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </div>

        
          <!--Column-->
          <div class="column col-xl-3 col-lg-6 col-md-6 col-sm-12">
          
          </div>

            <!--Column-->
          <div class="column col-xl-3 col-lg-6 col-md-6 col-sm-12">
           
          </div>

            <!--Column-->
          <div class="column col-xl-3 col-lg-6 col-md-6 col-sm-12">
            <div class="footer-widget info-widget">
              <div class="widget-content">
                <h6>Contact</h6>
                <ul class="contact-info">
                  <li class="address"><span class="icon flaticon-pin-1"></span> 66 Broklyn Street,
                    New York <br>United States of America</li>
                  <li><span class="icon flaticon-call"></span><a href="tel:666888000">666 888
                    000</a></li>
                  <li><span class="icon flaticon-email-2"></span><a
                    href="mailto:needhelp@linoor.com">needhelp@linoor.com</a></li>
                </ul>
                 <ul class="social-links clearfix">
                  <li><a href="#"><span class="fab fa-facebook-square"></span></a></li>
                  <li><a href="#"><span class="fab fa-twitter"></span></a></li>
                  <li><a href="#"><span class="fab fa-instagram"></span></a></li>
                  <li><a href="#"><span class="fab fa-pinterest-p"></span></a></li>
                </ul>
              </div>
            </div>
          </div>


        </div>

      </div>
    </div>

    <!-- Footer Bottom -->
    <div class="footer-bottom">
      <div class="auto-container">
        <div class="inner clearfix">
          <div class="copyright">&copy; Политика Конфеденциальности</div>
          <div class="copyright">Разработка EvoDevs</div>
        </div>
      </div>
    </div>

  </footer>

    <a @click="scrollTop" class="scroll-to-target scroll-to-top" :style="`display: ${scrollBtn ? 'inline' : 'none'}`" href="#"><i class="fa fa-angle-up"></i></a>

  </div>

</template>

<script>
  export default {
    name: "Footer",
    data(){
      return {
        scrollBtn: false
      }
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll);
    },

    methods: {

      handleScroll () {

        if (window.scrollY > 70) {
          this.scrollBtn = true
        }
        else if (window.scrollY < 70) {
          this.scrollBtn = false
        }
      },

      scrollTop () {
        window.scrollTo(0, 0);
      }


    }
  }
</script>

<style scoped>

</style>
