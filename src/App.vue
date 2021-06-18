<template>

<div id="app">
  <!-- <h1>Conversor de moedas</h1>
  <div class="grid">
     <Conversor moedaA="USD" moedaB="BRL"/>
      <Conversor moedaA="BRL" moedaB="USD"/>   
  </div>
   <div class="grid">
     <Conversor moedaA="EUR" moedaB="BRL"/>
     <Conversor moedaA="BRL" moedaB="EUR"/>
  </div>




  <div class="all">
    <h1>REAL to ALL</h1>
    <Conversor-two moedaB="EUR" moedaC="USD" />
  </div>


  <div class="all2" >
      <Form ></Form>
  </div> -->



  <div class="poke">
    <PokeSearch> </PokeSearch>
  </div>



</div>
  
 
</template>

<script>

// import Conversor from './components/Conversor.vue'
// import ConversorTwo from './components/ConversorTwo.vue'
// import Form from './components/Form.vue'
import PokeSearch from './components/PokeSearch.vue'


export default {
  name: 'App',
  components: {
  //  Conversor,
  //  ConversorTwo,
  //  Form,
    PokeSearch
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  /* margin-top: 60px; */
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(to right, #ffe259, #ffa751);
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


.grid{
  width: 100%;
  height: 50%;

  display: flex;
  justify-content: center;
  gap: 20px;
  align-items: center;
  flex-wrap: wrap;

}


.all{
  width: 100%;
  height: 100vh;
  background-color: rgb(155, 155, 155);
}

.all2{
  width: 100%;
  height: 100vh;
  background-color: rgb(122, 5, 5);
}



.poke{
  width: 100%;
  height: auto;
  background: linear-gradient(to right, #ffe259, #ffa751);
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  margin-top: 10px;
}
</style>
