<template>
    <div>
        <!-- Start Page Title Area -->
        <div class="page-title-area">
            <div class="container">
                <ul>
                    <li><nuxt-link to="/">Home</nuxt-link></li>
                    <li>Cart</li>
                </ul>
            </div>
        </div>
        <!-- End Page Title Area -->

        <!-- Start Checkout Area -->
		<section class="checkout-area ptb-60">
            <div class="container">
                <div class="row">
                    <div class="col-lg-12 col-md-12">
                        <div class="user-actions">
                            <i class="fas fa-sign-in-alt"></i>
                            <span>Returning customer? <nuxt-link to="/login">Click here to login</nuxt-link></span>
                        </div>
                    </div>
                </div>

                <form>
                    <div class="block">
                        <div class="col-lg-6 col-md-12">
                            <div class="billing-details">
                                <h3 class="title">Оформление заказа</h3>

                                <div class="row">
                                    <div class="col-lg-12 col-md-6">
                                        <div class="form-group">
                                            <label>Имя <span class="required">*</span></label>
                                            <input type="text" id="fullName" v-model="personDetails.fullName" class="form-control">
                                        </div>
                                    </div>

                                    <div class="col-lg-12 col-md-6">
                                        <div class="form-group">
                                            <label>E-mail<span class="required">*</span></label>
                                            <input type="email" id="address" v-model="personDetails.address" class="form-control">
                                        </div>
                                    </div>

                                    <div class="col-lg-12 col-md-6">
                                        <div class="form-group">
                                            <label>Телефон<span class="required">*</span></label>
                                            <input type="text" id="phone" v-model="personDetails.phone" class="form-control">
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                          <div class="col-lg-6 col-md-12">
                            <div class="billing-details order-details">

                                <h3 class="title">Доставка</h3>

                                <div class="row">
                                    <div class="col-lg-12 col-md-6">
                                        <div class="form-group">
                                            <label>Страна <span class="required">*</span></label>
                                            <input type="text" id="fullName" v-model="personDetails.fullName" class="form-control">
                                        </div>
                                    </div>

                                    <div class="col-lg-12 col-md-6">
                                        <div class="form-group">
                                            <label>Город   <span class="required">*</span></label>
                                            <input type="email" id="address" v-model="personDetails.address" class="form-control">
                                        </div>
                                    </div>

                                    <div class="col-lg-12 col-md-6">
                                        <div class="form-group">
                                            <label>Улица<span class="required">*</span></label>
                                            <input type="text" id="phone" v-model="personDetails.phone" class="form-control">
                                        </div>
                                    </div>

                                    <div class="col-lg-6 col-md-6">
                                        <div class="form-group">
                                            <label>Дом<span class="required">*</span></label>
                                            <input type="email" id="email" v-model="personDetails.email" class="form-control">
                                        </div>
                                    </div>

                                    <div class="col-lg-6 col-md-6">
                                        <div class="form-group">
                                            <label>Квартира <span class="required">*</span></label>
                                            <input type="text" id="phone" v-model="personDetails.phone" class="form-control">
                                        </div>
                                    </div>
                                        <div class="col-lg-12 col-md-6">
                                        <div class="form-group">
                                            <label>Индекс<span class="required">*</span></label>
                                            <input type="email" id="address" v-model="personDetails.address" class="form-control">
                                        </div>
                                    </div>
                                </div>
                                    <div class="payment-method">
                                    <p>
                                        <input type="radio" id="direct-bank-transfer" name="radio-group" checked>
                                        <label for="direct-bank-transfer">Доставка курьером (по Кыргысзтану)</label>
                                    </p>
                                    <p>
                                        <input type="radio" id="paypal" name="radio-group">
                                        <label for="paypal">Доставка Курьером по Всему миру</label>
                                    </p>
                                    <p>
                                        <input type="radio" id="cash-on-delivery" name="radio-group">
                                        <label for="cash-on-delivery">Экспресс доставка (Авиалиния)</label>
                                    </p>
                                </div>
                            </div>
                        </div>

                        <div class="col-lg-6 col-md-12">
                            <div class="order-details">
                                <h3 class="title">Состав заказа</h3>
                                <div class="order-table table-responsive">
                                    <table class="table table-bordered">
                                        <thead>
                                            <tr>
                                                <th scope="col">Продукт</th>
                                                <th scope="col">Сумма</th>
                                            </tr>
                                        </thead>

                                        <div>

                                            <div v-for="(cart, i) in cart" :key="i">
                                                <span class="product-name">
                                                    <a href="#">{{cart.name}}</a>
                                                </span>

                                                <span class="product-total">
                                                    <span class="subtotal-amount">${{cart.price * cart.quantity}}</span>
                                                </span>
                                            </div>
                                            
                                            <div>
                                                <span class="order-subtotal">
                                                    <span>Стоимость товаров:</span>
                                                </span>

                                                <span class="order-subtotal-price">
                                                    <span class="order-subtotal-amount">${{cartTotal}}</span>
                                                </span>
                                            </div>
                                            <div>
                                                <span class="order-shipping">
                                                    <span>Доставка:</span>
                                                </span>

                                                <span class="shipping-price">
                                                    <span>$10.00</span>
                                                </span>
                                            </div>
                                            <div>
                                                <span class="total-price">
                                                    <span>Итого:</span>
                                                </span>

                                                <span class="product-subtotal">
                                                    <span class="subtotal-amount">${{parseFloat(cartTotal + 10).toFixed(2)}}</span>
                                                </span>
                                            </div>
                                        </div>
                                    </table>
                                </div>

                            

                                <a href="javascript:void(0)" @click="add" class="btn btn-primary order-btn">Оформить заказ</a>
                            </div>
                        </div>
                    </div>
                </form>
            </div>
        </section>
		<!-- End Checkout Area -->
    </div>
</template>

<script>

export default {
    data(){
        return{
            personDetails: {
                fullName: 'John Doe', 
                address: 'Town hall, av 02',
                city: 'New York',
                email: 'john@gmail.com',
                phone: '+990198378372',
                createdAt: new Date()
            }
        }
    },
    computed: {
        cart(){
            return this.$store.getters.cart
        },
        cartTotal(){
            return this.$store.getters.totalAmount
        }
    }, 
    methods: {
        
    }
}
</script>