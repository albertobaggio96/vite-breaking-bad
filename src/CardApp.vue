<script>
import {store} from "./store.js";

export default {
  data(){
    return{
      store
    }
  },
}
//         {
//             "id": 34541863,
//             "name": "\"A\" Cell Breeding Device",
//             "type": "Spell Card",
//             "frameType": "spell",
//             "desc": "During each of your Standby Phases, put 1 A-Counter on 1 face-up monster your opponent controls.",
//             "race": "Continuous",
//             "archetype": "Alien",
//             "card_sets": [
//                 {
//                     "set_name": "Force of the Breaker",
//                     "set_code": "FOTB-EN043",
//                     "set_rarity": "Common",
//                     "set_rarity_code": "(C)",
//                     "set_price": "1.31"
//                 }
//             ],
//             "card_images": [
//                 {
//                     "id": 34541863,
//                     "image_url": "https://images.ygoprodeck.com/images/cards/34541863.jpg",
//                     "image_url_small": "https://images.ygoprodeck.com/images/cards_small/34541863.jpg",
//                     "image_url_cropped": "https://images.ygoprodeck.com/images/cards_cropped/34541863.jpg"
//                 }
//             ],
//             "card_prices": [
//                 {
//                     "cardmarket_price": "0.21",
//                     "tcgplayer_price": "0.19",
//                     "ebay_price": "4.99",
//                     "amazon_price": "24.45",
//                     "coolstuffinc_price": "0.25"
//                 }
//             ]
//         },
</script>

<template>
  <article v-for="card in store.cardsList">
    <img :src="card.card_images[0].image_url" :alt="card.name">
    <h2>{{ card.name }}</h2>
    <h3>{{card.archetype}}</h3>
  </article>
</template>

<style lang="scss">
  
</style>