<template>
    <div :class="tob.instock ? 'green' :'overlay' ">

      
      <img v-bind:src="tob.image" class="proimg"/>
        <h2>{{tob.Name}}</h2>
        <h1><strong>{{tob.Price}}</strong></h1>
        <h2>Instock:{{tob.instock}}</h2>
    </div>
</template>
<script>

export default {
    name: 'SingleTobacco',
    props:{
        tob: Array
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
 
