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

<div class="container">
    <div class="row">
        <div class="col-6">
                <select class="form-select" aria-label="Default select example" id="filter">
  <option selected>Seleziona Archetipo</option>
  <option v-for="archetipo, index in store.Archetipo" :key="index" :value="archetipo.archetype_name">
        {{archetipo.archetype_name}}</option>
</select>
<div class="col-6">
<button class="btn btn-primary" @click="$emit('perform_search')"> ok</button>
</div>
        </div>
    </div>
</div>
</template>

<style lang="scss" scoped>
@use '../style/generals.scss' as *;
    
</style>