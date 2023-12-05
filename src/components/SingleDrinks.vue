<template>
    <div :class="drink.instock ? 'green' :'overlay' ">

      
      <img v-bind:src="drink.image" class="proimg"/>
        <h2>{{drink.Name}}</h2>
        <h1><strong>{{drink.Price}}</strong></h1>
        <h2>Instock:{{drink.instock}}</h2>
    </div>
</template>
<script>

export default {
    name: 'SingleDrinks',
    props:{
        drink: Array
    }
    
}

</script>

<style scoped>
.proimg{
  height:150px;
  width:150px;
}
.green{
  background-color: green;
}
h2{
    font-size: 1em;
}
h4{
  margin: 2px
}
div{
  padding: 1em;
  text-align: center;
  margin: 1em;
}

.overlay {
  background-color: rgba(255, 255, 255, 0.7); /* Adjust the opacity as needed */
  color:grey;
}
</style>
 
