<template>
        <div class=wrapper id="wraper" >
           
             <h1 class=header>Vnesi procent popusta ter ceno izdelka!</h1>

            <div class="popust">
                <h2 class="popustZnesek">Procent popusta</h2>

                    <b-input-group size="sm" prepend="%" class="i">
                         <b-form-input type="number"  max="100" min="0"  maxlenght=3 id="popust"  v-model="procent" required debounce="0" placeholder="vpisi koliko procentov" 
                         onkeyup="if(this.value<0){this.value= this.value * -1}"
                         @keypress="onlyNumber"
                         onchange="changeHandler(this)"
                          >
                             {{ procent }}
                         </b-form-input>
                     </b-input-group>


            </div>
            <div class="znesek">

                <h2 class="izdelekZnesek">Cena izdelka</h2>

                    <b-input-group size="sm" prepend="€">
                            <b-form-input type="number"  max=10000000 min=0   id="popust"  v-model="znesek" required debounce="0" placeholder="vpisi znesek izdelka" onkeyup="if(this.value<0){this.value= this.value * -1}"
                             @keypress="onlyNumber">
                                {{ znesek }}
                             </b-form-input>
                     </b-input-group>
             </div>


                <button class="btn" @click="racun" >Izračunaj!</button>
                

            
            <div class="rezultatPopusta">
                <p>Znesek popusta :</p>
                <h3 class="koncniPopust">{{koncniPopust}} <span class="kes">€</span></h3>
            </div>                

            <div class="rezultatKoncneCene">
                <p>Znižana cena :</p>
                <h4 class="" >{{koncneCene}} <span class="kes">€</span></h4>
            </div>

       </div>     
            
</template>
 

 <script>



    export default {
       

        name: "Calculator",
         data() {
             return {
                    procent:"",
                    znesek:"",
                    zmnozek:"",
                    koncniPopust:"" || 0,
                    koncneCene:"" || 0,
                    
                    
                    }
                 },
          methods: {
            racun(){
          
          this.zmnozek = ((this.znesek * this.procent) ); 
          this.koncniPopust = (parseFloat(this.zmnozek / 100).toFixed(2));
          this.koncneCene = (parseFloat(this.znesek - this.koncniPopust).toFixed(2));
                  }, 
            isInputNumber(evt){
                
                        var ch = String.fromCharCode(evt.which);
                        
                        if(!(/[0-9]/.test(ch))){
                            evt.preventDefault();
                        }
                        
            },
            onlyNumber ($event) {
                        let keyCode = ($event.keyCode ? $event.keyCode : $event.which);
                        if ((keyCode < 48 || keyCode > 57) && keyCode !== 46) { 
                            $event.preventDefault();
                        }
                              },
            }
            
            
    
            
               }
            
      
    
 </script>




<style  scoped>

.header { 
    font-size: 20px;
    color: #42b983;
    margin:20px 30px 0 30px;
}


.popust { 
    margin-top: 40px;
    margin-left:50px;
    margin-right :50px;
}

.popust h2 { 
   margin-bottom:20px;
   font-size:15px;
}

.znesek { 
    margin-top: 40px;
    margin-left:50px;
    margin-right :50px;
    
     }

.znesek h2 { 
    margin-bottom:20px;
    font-size:15px;
    
}

.btn { 
    margin-top:40px;
    padding:5px 10px 5px 10px;
    font-weight:500;
    background-color:#42b983; 
    color:whitesmoke; 
     box-shadow: 10px 8px 33px 1px rgba(108,117,125,0.69);
    -webkit-box-shadow: 10px 8px 33px 1px rgba(108,117,125,0.69);
    -moz-box-shadow: 10px 8px 33px 1px rgba(108,117,125,0.69);
}

.btn:hover {
    background-color:#1D6E49;
    color:white;

}

.rezultatPopusta { 
    margin-top:30px;
    margin-bottom:30px;
}
.rezultatPopusta p {
    margin-top:0px;
    font-size:15px;

}

.rezultatPopusta .kes {
    color:#42b983;
}

.koncnaCena { 
    margin-top:40px;
    font-size :30px;
    font-weight:800;
}

.b-input-group{ 
    box-shadow: 10px 8px 33px 1px rgba(108,117,125,0.69);
-webkit-box-shadow: 10px 8px 33px 1px rgba(108,117,125,0.69);
-moz-box-shadow: 10px 8px 33px 1px rgba(108,117,125,0.69);
}


.rezultatKoncneCene {
    margin-left:20px; 
    margin-right:20px; 
    padding:0px;
}

.rezultatKoncneCene h4{ 
    font-size: 35px;
    font-weight:600;

    
}

.rezultatKoncneCene .kes {
    color:#42b983;
    font-size:30px;
    font-weight:500;
}


.test { 
    color:#ccc;
}


</style>