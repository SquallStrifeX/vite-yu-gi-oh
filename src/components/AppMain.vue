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
     <div class="container container_main p-5">
        <div class="row">
            <div class="col-2" v-for="(card, index) in store.cardList" :key="index">
              {{card.name}}
                
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
    height: 1000px;
    .container_main{
        max-width: 991px;
        .row{
            background-color: white;
        }
    }
}
    
</style>