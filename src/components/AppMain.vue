<script>
import { store } from '../store.js';
import CharacterCard from '../components/CharacterCard.vue'

export default {
  name: 'AppMain',
  components:{
    CharacterCard
  },
  
  data() {
    return {
      store
    }
  }
}
</script>

<template lang="">
<main>
    <div>
     <div class="container container_main pt-5 pb-5 ">
        <div class="row">
            <CharacterCard v-for="(card, index) in store.cardList" :key="index" :card="card" :index="index" ></CharacterCard>
</div>
        </div>
     </div>
</main>
</template>

<style lang="scss" scoped>
@use '../style/generals.scss' as *;


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