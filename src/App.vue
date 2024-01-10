<script>
import axios from 'axios'
import { store } from './store.js'

import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

export default {
  components: {
    AppHeader,
    AppMain
  },
  data() {
    return {
      store
    }
  },
  methods: {
    getCardList(){
      axios.get(this.store.endpoint).then((response) => {
        console.log(response.data.results)
        this.store.cardList = response.data.results
        console.log('Contenuto di cardList:', this.store.cardList);
      })

    },
    
   

  },
  created() {
    this.getCardList();

  }
}

</script>

<template lang="">
    <AppHeader></AppHeader>
    <AppMain ></AppMain>
</template>

<style lang="scss" scoped>
  
</style>