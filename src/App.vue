<template>

  <!--Step 3 use the component-->
  <MyHeader storeName="Divya Merchants"/> 
  <ClothingBox :products=products />
 
</template>

<script>
// Step: 1 Import the components
import MyHeader from './components/MyHeader.vue'
import ClothingBox from './components/ClothingBox.vue'


export default{
  name: 'App',

  // Step 2: Register the components
  components:{
    MyHeader,
    ClothingBox
  },
  data(){
    return {
      products: []
    }
  },
  methods:{
    //promoises
    async fetchcloths(){
      const res = await fetch('https://webservice-backend.onrender.com/api');
      const data = await res.json()
      console.log(data)
      return data
    }
  },
  async created(){
      this.products = await this.fetchcloths();
  }

  // data() => this.data cloths
  // method => this.method => fetchcloths
  // life cycle hooks created() => call our method here

}
</script>


<style>


@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;

}


</style>