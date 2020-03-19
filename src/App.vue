<template>
  <v-app>
    
   

    <v-container >
      <v-layaout row wrap>
       <v-row no-gutters>
        <v-col
          cols="10"
          md="6"
        >
    <!--titulo--> 
        <v-flex md10>
          <v-card class='mb-5 pa-2' >
           <v-card-text class="title">
           <h2 class="red lighten-3 text-center"
 >Agrege un Producto</h2>
            
           </v-card-text>
           <v-flex md6>
             <h2 >Producto</h2>
             <v-text-field
            
            placeholder="Producto"
            v-model="producto"
          ></v-text-field>
          
             <h2 >Precio</h2>
             <v-text-field
             
           type="number"
            placeholder="Precio"
            v-model="precio"
            
          ></v-text-field>
           </v-flex>
             
            <div class="my-2">
            <v-btn x-large color="success" dark @click="agregar">Agregar</v-btn>
          </div>
          </v-card>
       

       
      
   </v-flex>
        </v-col>
        <v-col
          cols="10"
          md="6"
        >
       
   <v-flex md10>
     
     <v-card class='mb-3 pa-2'>
        <v-card-text class="title">
         <h2 class='red lighten-3 text-center'> Productos agregados</h2>
        
        </v-card-text>
        <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">Producto</th>
          <th class="text-left">Precio</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in lista" :key="item.producto">
          <td>{{ item.producto }}</td>
          <td>{{ item.precio }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
   <v-btn x-large color="success" dark @click="sumar">Sumar</v-btn>
   {{total}}

 
 
          </v-card>
   </v-flex>
        </v-col>
    </v-row>
    

   </v-layaout>
    </v-container>
    
    
  </v-app>

  
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
 data(){
    return{
      lista:[],
      
     name:"App",
    
    precio:'',
    producto:'',
    total:'0'
     
    }
  },
  methods:{

    agregar:function (){
      if(this.producto!="" && this.precio!=""){
        var nuev_prod= this.lista.push({producto: this.producto,precio:this.precio})
        this.precio=""
        this.producto=""
        this.total='0'
        this.total= this.total + this.precio
        return this.total 
      
      }
      else{
        alert("Ingrese Un producto")
      }

    
    },
     sumar:function(){
          this.total="0"
        
           for(item of this.precio){
                this.total = this.total + item.precio
            }
            return this.total + this.precio

        
          

        }
       
           
            
         
            
          
            
            
            

        
  

    },
     
    
    
  }
  
  

        
         



    
    
   
  
  
 
        

        
  

  
  
       

    



  

  
</script>
