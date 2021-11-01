<template>
    <div class="sidebar">
        <div class="sidebar__content">
            <div class="sidebar__content__filter">
                <h3 class="sidebar__content__title">
                    Фильтры
                </h3>    
                <div>
                    <input 
                    @input="Check" 
                    class="inp-cbx" id="cbx"
                     type="checkbox"
                     value=1
                     >
                     Aксесуары
                    </div> 
                     <div>
                    <input 
                    @input="Check" 
                    class="inp-cbx" id="cbx"
                     type="checkbox"
                     value=2>
                     Aксесуары
                    </div>           
                    
                                
                <div>
                   
                </div>
            </div>
            <div class="sidebar__content__filter">
                <h3 class="sidebar__content__title">
                  Цена ($): 10-300
                </h3>
                    <div class="sidebar__content__input">
                       От <input class="sidebar-input" type="number" v-model.number="minPrice" @change="InputChange" min="0">
                       До <input class="sidebar-input" type="number" v-model.number="maxPrice" @change="InputChange" max="10000">
                    </div>
                <div visible id="collapse-4">
                     <h3 class="sidebar__content__title">
                        Size
                        </h3>
                    <ul class="sidebar__content__size__ul">
                        <li class="sidebar__content__size__li">XS</li>
                        <li class="sidebar__content__size__li">XS</li>
                        <li class="sidebar__content__size__li">XS</li>
                    </ul>
                </div>
            </div>

            <div class="sidebar__content__filter">
                <h3  class="sidebar__content__title">
                    Color
                </h3>

                <div visible id="collapse-6">
                    <ul class="color-list-row">
                        <li><a href="#" title="Black" class="color-black"></a></li>
                        <li><a href="#" title="Red" class="color-red"></a></li>
                        <li><a href="#" title="Yellow" class="color-yellow"></a></li>
                        <li><a href="#" title="White" class="color-white"></a></li>
                        <li><a href="#" title="Blue" class="color-blue"></a></li>
                        <li><a href="#" title="Green" class="color-green"></a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:['minPrice','maxPrice'],
    methods:{
        Check(e){
            let value = e.target.value
            this.$emit('Check',value)
        },
        InputChange(){
            this.$emit('InputChange',this.maxPrice,this.minPrice)
        }
    },
}
</script>

<style scoped>
.sidebar-input{
    width:40px;
    border:1px solid #C4C4C4;
    height:20px;
    color:black;
    font-size:16px;
    border-radius:5px;

}
.sidebar__content__input{
    display: flex;
    align-items: center;
    justify-content: space-around;
}
.sidebar__content__size__ul{
    display: flex;
    flex-wrap:wrap;
    align-items: center;
    justify-content: center;
}
.sidebar__content__size__li{
    color:black;
    border:1px solid black;
    font-size:16px;
    margin:10px;
    padding:0px 8px;
    border-radius: 5px;
}
</style>