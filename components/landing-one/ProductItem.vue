<template>
   <div class="product-four-flex">
      <div class="product-four-box">
          <nuxt-link :to="`/product-details/${product.id}`"> <img  class="product-four-box-image" :src="`http://134.122.74.23/${product.photo.photo}`" :alt="product.name"> </nuxt-link> 
          <div class="product-four-box-bottom">
              <nuxt-link  :to="`/product-details/${product.id}`"> <p class="product-four-box-title">{{lang ? product.title_ru : product.title_en}}</p></nuxt-link>
              <div class="product-four-bott">
                  <p class="product-four-box-price-kgs">{{lang ? product.price_kgs : product.price_usd}}{{lang ? 'сом' : '$'}}</p>
                   <p class="product-four-box-price-usd">6000 сом</p>
                    <p class="product-four-box-price-bel">70$</p>
              </div>
          </div>
      </div>
    </div>
</template>

<script>
import Timer from './Timer';
export default {
    name: 'ProductItem',
    components: {
        Timer
    },
    data(){
        return {
            getExistPId: null
        }
    },
    props: ['product', 'className'],
    computed: {
        cart(){
            return this.$store.getters.cart
        },
        lang(){
            return this.$store.state.lang
        }
    },
    methods: {
        quickView(e){
            this.$emit('clicked')
        },
        addToCart(item){
            const product = [{
                id: item.id,
                name: item.title_ru,
                price: item.price_kgs,
                image: item.image,
                quantity: 1
            }]

            if(this.cart.length > 0){
                let id = item.id 
                this.getExistPId = id
                let cartIndex = this.cart.findIndex(cart => {
                    return cart.id == id
                })

                if(cartIndex == -1){
                    this.$store.dispatch('addToCart', product);
                    this.$toast("Добавлен в корзину", {
                        icon: 'fas fa-cart-plus'
                    });
                } else {
                    this.$store.dispatch('updateCart', {
                        id, unit: 1, cart: this.cart
                    });
                    this.$toast.info("Этот продукт уже добавлен в корзину");
                }
            } else {
                this.$store.dispatch('addToCart', product)
                this.$toast("Добавлен в корзину",{
                    icon: 'fas fa-cart-plus'
                });
            }
        }
    }
}
</script>

<style scoped>

 

.product-item {
  margin:10px;
}
.product-price-content{
    display: flex;
    align-items: center;
    justify-content:space-between;
}
.bottom-link{
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.product-button{
    background:#85664E;
    border-radius: 9px;
    border:1px solid #85664E;
    outline:none;
    padding:10px;text-align:center;
    color:white;
    transition:1.3 ease
}
.product-button:hover{
    transition:1.3 ease;
    background:white;
    border:1px solid #85664E;
    color:#85664E;
}
</style>