<template>
  <section class="news-section">
    <div class="auto-container">

      <div class="row clearfix">
        <!--News Block-->
        <div v-for="pos in post" :key="pos.id" class="news-block col-lg-4 col-md-6 col-sm-12 wow fadeInUp animated" data-wow-delay="0ms" data-wow-duration="1500ms" style="visibility: visible; animation-duration: 1500ms; animation-delay: 0ms; animation-name: fadeInUp;">
          <div class="inner-box" @click="go(pos)"  >
            <div class="image-box">
              <img :src="`http://localhost:5000/${pos.image}`" alt="">
            </div>
            <div class="lower-box">
              <div class="post-meta">
                <ul class="clearfix">
                  <li><span class="far fa-clock"></span><li>{{pos.created}}</li>
                  <li><span class="far fa-user-circle"></span> Admin</li>
                  <li><span class="far fa-comments"></span> 2 Comments</li>
                </ul>
              </div>
              <h5>{{pos.title}}</h5>
              <div class="text">{{pos.content}}</div>
              <div class="link-box"><span class="flaticon-next-1"></span></div>
            </div>
          </div>
          
        </div>
      </div>
      <div class="more-box">
        <nuxt-link class="theme-btn btn-style-one" to="/blog">
          <i class="btn-curve"></i>
          <span class="btn-title">Load more posts</span>
         
        </nuxt-link>
      </div>
    </div>
  </section>
</template>

<script>
    export default {
        name: "BlogPage",
        data(){
          return{
            post:[]
          }
        },
       async mounted(){
       const po = await this.$axios.get('http://localhost:5000/api')
        this.post = po.data
        console.log(this.post)
        },
        methods:{
          go(pos){
            this.$router.push('/blog-grid/' + pos._id)
          }
        }
    }
</script>

<style scoped>

</style>
