<template>
    <div :class="milk.instock ? 'green' :'overlay' ">

      
      <img v-bind:src="milk.image" class="proimg"/>
        <h2>{{milk.Name}}</h2>
        <h1><strong>{{milk.Price}}</strong></h1>
        <h2>Instock:{{milk.instock}}</h2>
    </div>
</template>
<script>

export default {
    name: 'SingleMilkbread',
    props:{
        milk: Array
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
 
