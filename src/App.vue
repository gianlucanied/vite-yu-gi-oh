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
  },
  created(){
    this.getCard();
    this.getChoice();
    console.log(this.getChoice);
  },

 }
</script>

<template>
  <AppHeader message="Yu Gi Oh API"/>
  <main>
    <AppChoice/>
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