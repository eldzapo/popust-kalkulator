<template>
  <div class="hello">
    <h1>Kalkulator popusta</h1>
      <p> Ta kalkulator sem naredil z VueJs,Bootstrap <br>in Adobe Illustratorjem. </p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld'
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.hello p { 
    min-height: 100px;
    min-width: 100px;
    position:border-box;
    margin-top : 100px;
    font-size:25px;
    

}
.hello h1 { 
  font-size:80px;
  color:white;
  font-weight:bold;
   text-shadow:2px 2px 12px rgba(52,40,40,0.65);

  
}
.hello { 
  padding:70px 100px 150px 0;
  text-align: center;

} 
</style>
