<script>
import axios from 'axios';

import {store} from "./store.js";

import CardApp from './CardApp.vue';

export default {
  components:{
    CardApp
  },

  data(){
    return{
      store,
      apiSRC : "https://db.ygoprodeck.com/api/v7/cardinfo.php"
    }
  },
  methods:{
    getApi(){
      axios.get(this.apiSRC, {
        params: {
          num : 10,
          offset : 0
        }
      })
      .then((response) => {
        console.log(response);
        this.store.cardsList = response.data.data
        console.log(this.store.cardsList)
      })
      .catch(function (error) {
        console.log(error);
      })
      .then(function () {
        // always executed
      });  
    }
  },

  created(){
    this.getApi()
  }
}
</script>

<template>
  <main class="py-5">
    <div class="container bg-white px-5 pt-5">

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
  @use "./styles/partials/variables.scss" as *;

  main{
    background-color: $gold;

    #count{
      background-color: $count-color;
    }
    
  }
</style>