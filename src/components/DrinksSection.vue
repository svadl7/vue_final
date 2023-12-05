<template>
    <div class="conatiner">
        <div>
        <h1>Drinks</h1>
        <div v-for="drink of drinks" :key="drink.id" >
            <SingleDrinks :drink=drink />
        </div>

    </div>

    </div>
   
    
    
    
    
    
</template>


<script>
import SingleDrinks from './SingleDrinks.vue'
export default{

    name:'DrinksSection',
    props:{
        drinks:Array
    },
    components:{
        SingleDrinks
    }

}

</script>
<style scoped>
.conatiner
{
    width:100%;
}
div{
    text-align: center;
    display:inline-block;
    grid-area: "DrinksSection";
    color:brown;
}
</style>