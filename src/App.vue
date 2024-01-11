<script>
import axios from 'axios'
import { store } from './store.js'

import AppHeader from './components/AppHeader.vue'
import CharacterCard from './components/CharacterCard.vue'
import AppSearch from './components/AppSearch.vue'

export default {
  components: {
    AppHeader, 
    CharacterCard,
    AppSearch,

  },
  data() {
    return {
      store
    }
  },
  methods: {
    getCardList(){
   let ApiUrl = store.endpoint
    console.log(this.store.archetype)
    if(store.archetype == ''){


console.log(ApiUrl)}
else{
  ApiUrl = `https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.archetype}&num=100&offset=0`
}

      axios.get(ApiUrl).then((response) => {
        this.store.cardList = response.data.data
      })

    },
    getArchetypeList(){
      axios.get(store.archetipo_endpoint).then((response) => {
        store.Archetipo = response.data
      })

    },
    
   

  },
  created() {
    this.getCardList();
    this.getArchetypeList();

  }
}

</script>

<template lang="">
    <AppHeader></AppHeader>
    <main>
    <div>
      <AppSearch @perform_search="getCardList()"></AppSearch>
     <div class="container container_main pt-5 pb-5 ">
        <div class="row">
            <CharacterCard v-for="(card, index) in store.cardList" :key="index" :card="card" :index="index" ></CharacterCard>
</div>
        </div>
     </div>
</main>
</template>

<style lang="scss" scoped>
  
main { 
     background-color: sandybrown;
    .container_main{
        max-width: 991px;
        .row{
            background-color: white;
        }
    }
}



</style>