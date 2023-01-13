<script>
import axios from 'axios';

import {store} from "../store.js";

import CardApp from './main/CardApp.vue';
import LoadApp from './main/LoadApp.vue';
import OptionsApp from './main/OptionsApp.vue';

export default {
  components:{
    CardApp,
    LoadApp,
    OptionsApp,
  },

  data(){
    return{
      store,
      apiSRC : "https://db.ygoprodeck.com/api/v7/cardinfo.php",
      load : true,
      archetypeList: ['Alien', 'Laval', 'Vylon', 'Inzektor', 'Umi', 'Gusto'],
      
    }
  },
  methods:{
    getApi(value){
      axios.get(this.apiSRC, {
        params: {
          num : 10,
          offset : 0,
          archetype : value,
        }
      })
      .then((response) => {
        this.store.cardsList = response.data.data
      })
      .catch(function (error) {
        console.log(error);
      })
    },
    
    endLoad(){
      this.load = false
    },
  },
  
  created(){
    setTimeout(this.endLoad, 1000),
    this.getApi()

  }
}
</script>

<template>
  <main class="py-5">
   
    <OptionsApp :archetypeList="archetypeList" @getOptions="getApi"/>
    
    <LoadApp v-if="load"/>
        
    <div v-else class="container bg-white px-5 pt-5">

        <section id="count">
          <div class="fw-bolder text-white mb-0 ps-3 py-4">Found {{ store.cardsList.length }} cards</div>
        </section>
  
        <section id="cards" class="d-flex justify-content-between flex-wrap">
          <CardApp/>
        </section>
    </div>
  </main>
</template>

<style lang="scss">
  @use "../styles/partials/variables" as *;

  main{
    background-color: $gold;

    #count{
      background-color: $count-color;
    }
    
  }
</style>