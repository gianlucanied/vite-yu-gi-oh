<script>
 import axios from 'axios';
 import AppHeader from './components/AppHeader.vue'
 import CharactersList from './components/CharactersList.vue'
 import AppChoice from './components/AppChoice.vue'

 import {store} from './store'

 export default {
  components: {
    AppHeader,
    CharactersList,
    AppChoice
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
        store.cards = res.data.data
      }))
      .catch((err)=>{
        console.log("Errori", err);
      })
    },
    getChoice(){
      axios
      .get(store.apiUrlChoice)
      .then((res => {
        store.choices = res.data
        console.log(res.data);
      }))
      .catch((err)=>{
        console.log("Archetipi non trovati", err);
      })
    },
    selectCards(event){
      axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype="+event.target.value)
      .then((res => {
        console.log("store", store.cards);
        store.cards = res.data.data
        console.log("res", res.data);
        
      }))
      .catch((err)=>{
        console.log("Errori", err);
      })
    }
  },
  created(){
    this.getCard();
    this.getChoice();
  },

 }
</script>

<template>
  <AppHeader message="Yu Gi Oh API"/>
  <main>
    <AppChoice @change="selectCards"/>
    <div class="container">
      <CharactersList/>
    </div>
  </main>

</template>

<style lang= "scss">
@use './styles/general.scss';
main {
  background-color: orange;
  padding-top: 7%;
}
</style>