<template>
    <div class="all-product">
         <div class="products-filter-options">
            <div class="product-filter-navbar">
               Menu
            </div>
             <div class="product-filter-sort">
                    <div class="products-ordering-list">
                        Сортировать по:
                        <select>
                            <option value="1">Популярности</option>
                            <option @click="Price" value="2">Цене</option>
                            <option value="3">По алфавиту</option>
                        </select>
                    </div>
                </div>
            </div>
        <div id="products-filter" class="products-collections-listing row">
            <ProductItem
                v-for="(product, index) in products"
                :product="product"
                :key="index"
                @clicked="toggle"
                :className="`col-lg-4 col-md-6 products-col-item`"
            ></ProductItem>
            
        </div>
        <nav class="product-nav">
            <ul class="nav-item">
                <li class="nav-item-list nav-active">Назад</li>
                <li class="nav-item-list  nav-active">1</li>
                <li class="nav-item-list"><span class="page-numbers current">2</span></li>
                <li class="nav-item-list">3</li>
                <li class="nav-item-list">4</li>
                <li class="nav-item-list"> <span class="page-numbers dots">…</span></li>
                <li class="nav-item-list">11</li>
                <li class="nav-item-list">12</li>
                <li class="nav-item-list  nav-active">Вперед</li>
            </ul>
        </nav>
        <QuckView />
    </div>
</template>

<script>
import QuckView from '../modals/QuckView';
import { mutations } from '../../utils/sidebar-util';
import ProductItem from '../landing-one/ProductItem';
export default {
    components: {
        QuckView,
        ProductItem
    },
    methods: {
        toggle() {
            mutations.toggleQuickView();
        },
        Price(){
            this.$emit('Price')
        }
    },
  props:{
      products:{
          type:Array,
      }
  }
}
</script>
<style scoped>
.nav-item {
    margin-top:60px;
    display: flex;
    align-items: center;
    justify-content: center;
    
}
.nav-item-list{
    border:1px solid #85664E;
    padding:8px 14px;
    text-align:center;
    margin:10px;
    border-radius: 7px;
}
.nav-active{
    background-color:#85664E;
    color:white;
    font-weight:500;
    border-radius: 7px;
}
.products-filter-options{
    display: flex;
    align-items: center;
    justify-content: space-between;
}
@media only screen and (max-width: 599px){
     .nav-item-list{
		margin:5px;
		padding:8px;
	  }
	  .nav-item{
		  display: flex;
		  align-items:center;
	  }
}
</style>