<template>
  <div>
      <div class="checkout">
          <h3>Оформление заказа</h3>
          <form class="checkout-form" >
            <div class="checkout-form-top">
                  <p>Данные покупателя</p>
              <label for="email">Имя</label>
              <input style="border:1px solid black" class="form-input" type="text">
              <label for="email">E-mail</label>
              <input style="border:1px solid black" type="text">
              <label for="email">Телефон *</label>
              <input style="border:1px solid black" type="text">
            </div>
            <div class="checkout-form-middle">
                <p>Доставка</p>
                <a href="/">Подробнее узнать об<span>Условиях доставки</span></a>
                <label for="email">Страна</label>
              <input style="border:1px solid black" class="input" type="text">
               <label for="email">Город</label>   
              <input style="border:1px solid black" type="text">
               <label for="email">Улица</label>
              <input style="border:1px solid black" type="text">
              <div class="flex">
                   <label for="email">Дом</label>
              <input style="border:1px solid black" type="text"> <label for="email">Квартира</label>
              <input type="text">
              </div>
               <label for="email">Индекс</label>
              <input type="text">
               <input type="checkbox">Доставка курьером (по Кыргысзтану)
               <input type="checkbox">Доставка курьером (по Кыргысзтану)
               <input type="checkbox">Доставка курьером (по Кыргысзтану)
            </div>
            <div class="checkout-bottom">
                <h3>Состав заказа</h3>
                <div class="checkout-bottom-content">
                    <div>
                        <img src="" alt="">
                    </div>
                    <div class="checkout-bottom-info">
                        <p>Свитер бренда Х</p>
                        <span>Цвет:</span>
                         <span>Размер:</span>
                        <span>K-do:</span>
                        <div>
                            <span>6000 сом</span>
                            <button>Удалить</button>
                        </div>                        
                    </div>
                </div>
            </div>
            <div class="checkout-bottom-bottom">
                <div class="flex">
                    <p>Стоимость товаров:</p>
                     <p>18000 сом</p>  
                </div>
                <div class="flex">
                    <p>Доставка::</p>
                     <p>1800 сом</p>  
                </div>
                 <div class="flex">
                    <p>Итого:</p>
                     <p>1800 сом</p>  
                </div>
                <input type="check">Нажимая «Оформить заказ», я выражаю согласие с политикой обработки персональных данных
            </div>
            <router-link to="/sank"><button>Оформить заказ</button></router-link>
          </form>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.checkout{
    display: flex;
    flex-direction:column;
    align-items: center;
    margin:0 auto;
    text-align:flex-start;
};
.form-input{
    border:1px solid black;
    border-radius: 2px;
    padding:4px;
};
.checkout-form{
    display: flex;
    flex-direction:column;
    align-items: center;
    margin:0 auto;
}
.checkout-form-top{
    display: flex;
    flex-direction:column;
}
.checkout-form-middle{
     display: flex;
    flex-direction:column;
}
.checkout-bottom-content{
    display: flex;
}
.flex{
    display: flex;
}

</style>