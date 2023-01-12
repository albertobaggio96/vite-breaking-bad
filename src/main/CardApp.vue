<script>
import {store} from "../store.js";

export default {
  data(){
    return{
      store
    }
  },
}
</script>

<template>
  <article v-for="card in store.cardsList" class="mb-3">
    <img :src="card.card_images[0].image_url" :alt="card.name" class="w-100">
    <h2 class="fs-5 text-center fw-bolder text-white">{{ card.name }}</h2>
    <h3 class="fs-5 text-center">{{card.archetype}}</h3>
  </article>
</template>

<style lang="scss">
  @use "../styles/partials/variables.scss" as *;

  article{
    width: calc(90% / 5);
    background-color: $gold;
  }
</style>