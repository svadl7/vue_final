<template>
    <div class="container">
        <div>
        <h1>Chips</h1>
        
        <div v-for="chip of chips" :key="chip.id" >
            <SingleChips :chip=chip />
        </div>

    </div>

    </div>
    
    
    
    
    
    
</template>


<script>
import SingleChips from './SingleChips.vue'
export default{

    name:'ChipsSection',
    props:{
        chips:Array
    },
    components:{
        SingleChips
    }

}

</script>
<style scoped>
.container{
    width:100%;
}
div{
    text-align: center;
    display: inline-block;
}

</style>
