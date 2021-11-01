<template>
  <div class="page-wrapper">
    <Nav />
      <nuxt />
    <Footer />
  </div>
</template>


<script>
import Nav from '../components/Nav.vue'
import Footer from '../components/Footer.vue'
  export default {
    components: {
      Nav,Footer
    },
    head(){
      return {
        title: "Manzoni- Онлайн магазин"
      }
    },
    mounted(){
      this.$nextTick(() => {
        this.$nuxt.$loading.start()
        setTimeout(() => this.$nuxt.$loading.finish(), 500)
      })
    }
  }
</script>

<style>
</style>
