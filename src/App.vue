<template>
  <div id="app">
    <b-container>
      <br-row>
          <HelloWorld />
        <b-col sm="8" offset-sm="3">
           <div class="jumbo">
                <Calculator />
            </div>      
        </b-col>  
        </br-row>
    </b-container>
  </div>
</template>

<script>

import Calculator from './components/Calculator.vue'


export default {
  name: 'App',
  components: {
    
    Calculator
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding:100px;
  background-image: url("./assets/bg-01.png");
  background-size:cover;
  
}
.jumbo {
  background-color:#f2f2f2;
  width: 450px;
  height: auto;
  padding:40px 30px 40px 30px;
  border-radius:30px;
  box-shadow: 10px 8px 33px 1px rgba(108,117,125,0.36);
-webkit-box-shadow: 10px 8px 33px 1px rgba(108,117,125,0.36);
-moz-box-shadow: 10px 8px 33px 1px rgba(108,117,125,0.36);
}

</style>
