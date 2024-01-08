<script>
import SingleCard from './SingleCard.Vue'

import {store} from '../store'
export default{
    name: 'CharactersList',
    components: {
        SingleCard
    },
    data() {
    return {
      store,
    }
  },
}
</script>

<template>
    <section class="container">
        <div v-for="card in store.cards" :key="card.id" class="col-4">
            <SingleCard :info="card"/>
            <!-- {{ card.name }} -->
        </div>
    </section>
</template>

<style lang="scss" scoped>
</style>