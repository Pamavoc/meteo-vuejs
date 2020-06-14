<template>
    


    <div class="container">
        <h1 class="my-4">App Meteo Vue.js</h1>

        <div class="form-groupe mb-5">
            <label for="position">Ville</label>
            <input v-model="requete" @keypress.enter="goMeteo" type="text" id="position" class="form-control">
        </div>
    
        <div v-if="temps" class="w-75 m-auto" >
                <h3 class="text-center mb-3">Position : {{ temps.name }} </h3>
            <div class="card text-center p-5">
                <p class="texte-affichage">Temperature :{{ temps.main.temp }} </p>
                <p class="texte-affichage">Temps : {{ temps.weather[0].description }} </p>
            </div>
        </div>
    
    </div>

    

</template>

<script>

import axios from 'axios'


require('dotenv').config()


export default {

    name: 'Meteo',
    data(){
    return {
      requete: '',
      temps: undefined, //objet de données
      api_code: process.env.VUE_APP_KEY,
      url_looking: `https://api.openweathermap.org/data/2.5/weather?`
    }
  },

  methods: {
    goMeteo() {
    
        axios
        .get(`${this.url_looking}q=${this.requete}&units=metric&APPID=${this.api_code}&lang=fr`)
        .then(response =>{
          //console.log(response)

          this.temps = response.data;
         console.log(this.temps);
        })
         this.requete = ''
      
    }
  }
}


</script>

<style scoped>

.texte-affichage {
    font-size:30px;
    font-weight:300;
    line-height: 1.2;
}


</style>