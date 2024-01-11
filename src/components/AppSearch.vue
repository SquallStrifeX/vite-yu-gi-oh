<script>
import { store } from '../store.js'
export default {
    name: 'AppSearch',
    
    data() {
        return {
            store,
        }
    },
}
</script>

<template lang="">

<div class="container container_main pt-5">
    <div class="row">
        <div class="col-6">
                <select class="form-select" aria-label="Default select example" id="filter" v-model="store.archetype">
  <option selected >Seleziona Archetipo</option>
  <option v-for="archetipo, index in store.Archetipo" :key="index" >
        {{archetipo.archetype_name}}</option>
</select>
</div>
<div class="col-5">
<button class="btn btn-primary" @click="$emit('perform_search')" > Ricerca</button>
</div>
    </div>
</div>
</template>

<style lang="scss" scoped>
@use '../style/generals.scss' as *;
.container_main{
        max-width: 991px;}
</style>