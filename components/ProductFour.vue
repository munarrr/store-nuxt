<template>
  <div class="product-four">
      <h3 class="product-four-title">Выбрать категорию:<nuxt-link to="/products"><span>свитер</span></nuxt-link></h3>
    <div class="product-four-flex">
         <div class="product-four-box" v-for="products in getFourProduct" :key="products.id">
         <nuxt-link :to="`/product-details/${products.id}`"> <img  class="product-four-box-image" :src="`http://134.122.74.23/${products.photo.photo}`" :alt="products.name"> </nuxt-link> 
          <div class="product-four-box-bottom">
              <!-- <p class="product-four-box-title">{{products.title_ru}}</p> -->
              <div class="product-four-bott">
                  <p class="product-four-box-price-kgs">{{products.price_kgs}}</p>
                   <p class="product-four-box-price-usd">{{products.price_usd}}</p>
                    <p class="product-four-box-price-bel">70$</p>
              </div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
  import {mapActions,mapGetters} from 'vuex'
export default {
 methods: {
      ...mapActions(['getOrder'])
    },
    mounted(){
      this.getOrder()
    },
    computed:{
    ...mapGetters(['getFourProduct'])   
    }
}
</script>

<style>
.product-four{
    width:80%;
    margin:0 auto;
    margin: 80px auto;
}
.product-four-flex{
    display: flex;
    align-items: center;
    justify-content: center;
}
.product-four-box{
    margin:10px;
    display: flex;
    flex-direction: column;
}
.product-four-box-bottom{
    display: flex;
    justify-content: space-between;
    margin-top:25px;
}
.product-four-box-image{
    max-width: 100%;
    width:300px;
    height:400px;
    object-fit:cover;
}
.product-four-title{
    font-size:14px;
    font-weight: 300;
    margin-bottom:40px;
    text-align:center;
}
.product-four-box-price-kgs{
    font-size:16px;
    font-weight: 500;
    color:black;
    margin:3px;
    line-height: 0;
}
.product-four-box-price-usd{
    font-size:16px;
    font-weight: 500;
    color:#686868;
    margin:3px;
    text-decoration: line-through;
}
.product-four-box-price-bel{
    color:#686868;
     font-size:16px;
    font-weight: 500;
    margin:3px;
    line-height: 0;
}

.product-four-box-title{
    font-size:16px;
    font-weight: 500;
    color:black;
}
@media only screen and (max-width:769px){
    .product-four-flex{
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction:column;
}
}
</style>