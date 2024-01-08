<script>
 import AppHeader from './components/AppHeader.vue'
 import CharactersList from './components/CharactersList.vue'


 export default {
  components: {
    AppHeader,
    CharactersList
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
