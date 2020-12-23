<template>
  <div id="app">
    <b-container>
      
          <b-row >
                <b-col id="hello-wrapper" class="col-lg-7 col-md-7 col-sm-12 col-xs-12"   >
                    <HelloWorld /> 
                </b-col>

                <b-col id="jumbo"         class="col-lg-5 col-md-5 col-sm-12 col-xs-12"> 
                   <Calculator />    
                </b-col>    
          </b-row>
        
    </b-container>
  </div>
</template>

<script>

import Calculator from './components/Calculator.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    
    Calculator,
    HelloWorld
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
  padding:132.5px 20px 132.5px 20px ;
  

}
#jumbo {
  background-color:#f2f2f2;
  width: auto;
  height: auto;
  padding:40px 30px 40px 30px;
  border-radius:30px;
  margin:0px;
  box-shadow: 3px 2px 28px 5px rgba(52,40,40,0.53);}

#hello-wrapper {
    display:-moz-box;
    object-position: center;
    margin-left :50% auto;
    margin-right:50% auto;

}

</style>
