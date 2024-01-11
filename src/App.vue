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
      axios.get(store.endpoint).then((response) => {
        this.store.cardList = response.data.data
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