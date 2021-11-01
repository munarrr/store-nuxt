<template>
    <div>   
        <div class="flex-container">
            <div class="flex-container-item1"> 
                <Sidebar :maxPrice="maxPrice" :minPrice="minPrice" @InputChange="InputChange(item,val)" @Check="Check" :products="getProduct" />
            </div>
            <div :lang="lang" class="flex-container-item2"> 
                 <AllProducts @Price="Price" :products="getProduct" />
            </div>
        </div>
    </div>   
</template>

<script>
import Sidebar from '../components/all-products/Sidebar';
import AllProducts from '../components/all-products/AllProducts';
import {mapActions,mapGetters} from 'vuex'
export default {
    components: {
        Sidebar, AllProducts,
    },
    data(){
        return{
            sortTedProduct:[],
             minPrice:0,
             maxPrice:10000,
             lang:false
        }
    },
      computed: {
          ...mapGetters(['getProduct']),       
       
        fiterProducts(){
            let vm = this
            if(this.sortTedProduct.length){
                return this.sortTedProduct
            }else{
                return this.products
            }
        },
        Sort(){
            this.Price()
        }
    },
    methods: {
        Check(e){
           const sortedProduct = this.getProduct.filter(item => item.category === e)
           console.log(e,sortedProduct)


        },
        Price(){
            if(this.getProduct.price_kgs || this.getProduct.price_usd){
                this.sortTedProduct.push(this.getProduct.price_kgs.sort((a,b) => (a-b)))
            }
            else this.sortTedProduct.push(this.getProduct)
        },
        InputChange(item,val){
            console.log(item)
        },
       ...mapActions(['getOrder']),
        
    },
    mounted(){
        this.getOrder()
        console.log('asaa')
    }
}
</script>