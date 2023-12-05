<template>
  <!-- Step , you must use the component -->
  <div class="conatiner">
    <header class="head">
      <div class="name">
        <MyHeader shopName="Fresh groceries" address="Time Square,New York" />

      </div>
      
      <div class="menu">
        <a href="#chi" class="link">Chips</a>
        <a href="#dri" class="link">Drinks</a>
        <a href="#tob" class="link">Tobacco</a>
        <a href="#milk" class="link">Milk Products</a>

      </div>

    </header>
    <div class="chips" id="chi">
      <ChipsSection :chips=chipsData />

    </div>
    <div class="drinks" id="dri">
      <DrinksSection :drinks=drinksData />

    </div>
    <div class="tobacco" id="tob">
      <TobaccoSection :tobacco=tobaccoData />

    </div>
    <div class="milkproducts" id="milk">
      <MilkBreadSection :milkbread=milkbreadData />

    </div>
      
  
    
  </div>
    
   

  

 
 

 

</template>

<script>

// step 1 import the child component
import MyHeader from './components/MyHeader.vue'
import ChipsSection from './components/ChipsSection.vue'
import DrinksSection from './components/DrinksSection.vue'
import TobaccoSection from './components/TobaccoSection.vue'
import MilkBreadSection from './components/MilkBreadSection.vue'
// 

export default{
 name: 'App',
 // step 2: register the component 
 components:{
   MyHeader,
   DrinksSection,
   ChipsSection,
   TobaccoSection,
   MilkBreadSection
 },
 data() {
    return {
      chipsData: [],
      drinksData: [],
      tobaccoData: [],
      milkbreadData: []
    }
  },
  methods: {
    async fetch() {
      try {
        const res = await fetch("https://sai-jaswanth-final.onrender.com/api");
        const data = await res.json();
        return data;
      } catch (error) {
        console.error('Error fetching data:', error);
        return [];
      }
    },
  },

  async created() {
    const rawData = await this.fetch();

    // Assuming rawData is an array with a single object containing different categories
    if (rawData.length > 0) {
      const categories = Object.keys(rawData[0]);
      categories.forEach(category => {
        this[`${category.toLowerCase()}Data`] = rawData[0][category];
      });
    }
  }
}


</script>


<style>
.container {
  display: grid;
  grid-template-columns:1fr;
  grid-template-rows: 0.3fr 1fr 1fr 1fr 1fr;
  grid-template-areas: 
  "head"
  "chips"
  "drinks"
  "tobacco"
  "milkproducts";
  height:100vh;
  width:auto;
  background-color:#FFFDD0;
  color:brown
  
  /* Add other styling as needed */
}
.head {
  grid-area: head;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: orange;
  margin:10px;
}
.link{
  color:black;
  padding:20px;
  text-decoration: none;
  font-size: x-large;
  font-weight: bold;
}
.name{
  padding-left: 50px;

}
.menu{
  padding:20px;

}
.chips{
  grid-area: chips;
  max-height: 500px;
  margin:10px;
}
.drinks{
  grid-area:drinks;
  max-height: 500px;
  margin:10px;
}
.tobacco{
  grid-area:tobacco;
  max-height: 500px;
  margin:10px;
}
.milkproducts{
  grid-area: milkproducts;
  max-height:500px;
  margin:10px;
}

</style>