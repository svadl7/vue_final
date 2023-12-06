<template>
    <div class="container">
        <div>
        <h1>Tobacco</h1>
        
        <div v-for="tob of tobacco" :key="tob.id" >
            <SingleTobacco :tob=tob />
        </div>

    </div>

    </div>
  
    
    
    
    
    
</template>


<script>

import SingleTobacco from './SingleTobacco.vue'
export default{

    name:'TobaccoSection',
    props:{
        tobacco:Array
    },
    components:{
        SingleTobacco
    }

}

</script>
<style scoped>
.container
{
    width:100%;

}
div{
    text-align: center;
    display: inline-block;
}
</style>
