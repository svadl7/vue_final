<template>
    <div class="conatiner">
        <div>
        <h1>Milk & Bread</h1>
        
        <div v-for="milk of milkbread" :key="milk.id" >
            <SingleMilkbread :milk=milk />
        </div>

    </div>

    </div>
  
    
    
    
    
    
</template>


<script>
import SingleMilkbread from './SingleMilkbread.vue';
export default{

    name:'MilkBreadSection',
    props:{
        milkbread:Array
    },
    components:{
    SingleMilkbread
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
    color:brown;
}
</style>
