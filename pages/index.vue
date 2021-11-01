<template>
  <div>
 
    <BannerTwo />
    <ProductFour  />
    <About />
    <ParallaxSection />
     <div class="slide-item">
        <div class="image-layer2" style="background-image: url(/images/background/background.jpg);"></div>
     </div>
 
  </div>
</template>

<script>


  import BannerTwo from "../components/BannerTwo";
  import ProductFour from "../components/ProductFour.vue";
  import About from "../components/About";
  import LiveSection from "../components/LiveSection";
  import WedoSection from "../components/WedoSection";
  import FactSection from "../components/FactSection";
  import TrustedSection from "../components/TrustedSection";
  import TeamSection from "../components/TeamSection";
  import ParallaxSection from "../components/ParallaxSection";
  import BrandsSection from "../components/BrandsSection";
  import AgencySection from "../components/AgencySection";
  import BlogSection from "../components/BlogSection";
  import CallToAction from "../components/CallToAction";


  export default {
    components: {  
      CallToAction,
      BlogSection,
      AgencySection,
      BrandsSection,
      ParallaxSection,
      TeamSection,
      TrustedSection,
      FactSection,
      WedoSection,
      LiveSection,
      About,
      ProductFour,
      BannerTwo,
    },
   
  }
</script>
