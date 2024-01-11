<script>
import { store } from '../store.js';

export default {
  name: 'AppMain',
  
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
            <div class="col-2 nome_card p-0 mt-5" v-for="(card, index) in store.cardList" :key="index">
              <img class="img" v-for="card in card.card_images" :src="card.image_url" alt="">
              <div class=" m-3"> 
                <div >{{card.name}}</div> 
                <div class="archetype m-3">{{card.archetype}}</div> 
              </div>
             
                
            </div>
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

.img{
  max-width: 100%;

}

.nome_card{
  background-color: sandybrown;
  text-align: center;
  color: white;
  font-size: 15px;
  margin: 10px;
  width: calc(20% - 20px);
  .archetype{
    color: black;
    
  }
}
    
</style>