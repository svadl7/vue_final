<template>
  <div>
      <h1> {{shopName}} </h1>
      <h2> {{address}} </h2>

  </div>
</template>



<script>

export default{

  name:'MyHeader',
  props:{
      shopName: String,
      address: String
  }
}

</script>

<style scoped>
div{
  text-align: center;
  grid-area: "MyHeader";
}
</style>
