<template>
     <div class="card border-light p-1">



     <div v-if="error">Oops! Error encountered: {{ error.message }}</div>


          
     <div v-else-if="data">
    <div v-for="(value, name) in data" >     
      <h3 class="data"> {{name}} :</h3> 
      <div v-for="(v, n) in value" >
        <h3 class="subdata"> {{n}}:</h3> <br>
     <template v-if="typeof v === 'object'">
       <div v-if="n === 'fields'">
          <div v-for="(vh, nh) in v" >
           <span v-for="(vh, nh) in vh" class="fields">
             <span v-if="typeof vh === 'object'">
                <span class="fname" >{{nh}}: </span>
               <span v-for="(vh, nh) in vh">
                 <span>{{vh}},</span>
               </span>
             </span>
             <span v-else>
           <span class="fname" >{{nh}}: </span> 
           <span class="fvalue" >{{vh}} </span>
          </span>
           </span>


          </div>
          <br>
       </div>



       <div v-else>
      <div v-for="(vh, nh) in v" >
            <span v-for="vha in vh" >
            <span class="sv">{{vha}}</span>
            </span>
            <br>
      </div>
       </div>
     
    </template>


    <template v-else>
     <p class="single"> {{ v }} </p>
    </template>

     
      </div>
    </div>
  </div>



  <div v-else>Loading...</div>
         <img src="" alt="">


    </div>
</template>




<script setup>
    import { ref } from 'vue'
    
    // data un état du composant qui peut changer. Pour assigner une valeur à data  on écrit data.value ="une valeur"
    const data = ref(null)
    const error = ref(null)
    // requete sur un fichier JSON sur github
    // fetch est une fonction qui est présente dans le navigateur qui permet de faire des requêtes asynchrone avec une API HTTP distante
    // Then c'est resolue, la requête, et on peut chaîner avec un autre then pour moidifier la source, par exemple ici en transformant celle-ci en json. 
    // Le catch va gérer les éventuelels erreurs
    fetch( 'https://raw.githubusercontent.com/IBM/taxinomitis/master/resources/datasets/numbers/titanic.json' )
    .then((res) => res.json())
    .then((json) => {console.log(json); return json})
    .then((json) => (data.value = json))
    .catch((err) => (error.value = err))
</script>
<style scoped>
.data{
  color: blue;
    font-weight: 900;
}
.subdata{
  color: rgb(72, 223, 243);
    font-weight: 600;
}
.fields{   
    margin:15px;
}
.fname{
  color: rgb(43, 43, 141);
  font-weight: 600;
   margin-right:5px;
}
.fvalue{
  color: rgb(15, 15, 20);
  font-weight: 400;
}
.single{
  font-weight: 600;
}
.sv{
  
  font-weight: 600;
  margin: 10px;
}
</style>