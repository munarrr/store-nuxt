<template>
  <div>
            <div class="single">
                <div class="single-info">
                    <div class="single-image">
                        <img :src="`http://134.122.74.23/${product.photo.photo}`" alt="">
                    </div>
                    <div class="single-info-content">
                        <h4>{{product.title_ru}}</h4>
                        <div class="single-color">
                        <p>Цвет:</p>
                        <span></span>
                         <span></span>
                          <span></span>
                           <span></span>
                        </div>
                        <div class="single-size">
                        <p>Размер:</p>
                        <span>S</span>
                         <span>M</span>
                          <span>XL</span>
                           <span>XXL</span>
                        </div>
                        <div class="single-price">
                            <p>Цена:</p>
                            <h5 class="single-price-price">{{product.price_kgs}}</h5>
                        </div>
                        <button @click="addToCart(product)" class="single-button">Добавить в корзину</button>
                    </div>
                </div>
                 <div class="single-rew">
                     <div>
                          <a v-on:click="activetab=1" class="single-rew-tile" v-bind:class="[ activetab === 1 ? 'active' : '' ]">Описание</a>
                      <a v-on:click="activetab=2" class="single-rew-tile"  v-bind:class="[ activetab === 2 ? 'active' : '' ]">Отзывы</a>
                     </div>
                      <div>
                        <div  v-if="activetab === 1" class="tabcontent">
                           {{product.description_ru}}
                        </div>
                        <div v-if="activetab === 2" class="tabcontent">
                        csdcdsdcsdcsdc
                        </div>
                      </div>
                 </div>
            </div>
  </div>
</template>

<script>
export default {
    data(){
        return {
            id: this.$route.params.id,
             activetab: 1 
        }
    },
  computed: {
        product(){
            return this.$store.state.products.find(product => product.id === parseInt(this.id));
        },
         cart(){
            return this.$store.getters.cart
        },
    },
    methods:{
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

<style>

</style>