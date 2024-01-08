<script>
 import axios from 'axios';
 import AppHeader from './components/AppHeader.vue'
 import CharactersList from './components/CharactersList.vue'

 import {store} from './store'

 export default {
  components: {
    AppHeader,
    CharactersList
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCard(){
      axios
      .get(store.apiURL)
      .then((res => {
        // console.log(res.data.results);
        store.charactersList = res.data
      }))
      .catch((err)=>{
        console.log("Errori", err);
      })
    }
  },
  created(){
    this.getCard();
  }
 }
</script>

<template>
  <AppHeader message="Yu Gi Oh API"/>
  <main>
    <div class="container">
      <CharactersList/>
    </div>
  </main>

</template>

<style lang= "scss">
@use './styles/general.scss';
</style>
