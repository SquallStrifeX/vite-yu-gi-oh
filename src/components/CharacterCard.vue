<script>
export default {
    name: 'CharacterCard',
    props: {
        card: Array,

    },
}
</script>
<template lang="">
    <div class="col-2 nome_card p-0 mt-5">
              <img class="img" v-for="card in card.card_images" :src="card.image_url" alt="">
              <div class=" m-3"> 
                <div >{{card.name}}</div> 
                <div class="archetype m-3">{{card.archetype}}</div> 
              </div>
            </div>
</template>

<style lang="scss" scoped>
@use '../style/generals.scss' as *;
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
.img{
  max-width: 100%;

}
    
</style>