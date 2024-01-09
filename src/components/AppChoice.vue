<script>
  import { store } from '../store';
  
  export default {
    name: 'AppChoice',
    data() {
      return {
        store,
      };
    },
    methods: {
        emitChange(event){
            this.$emit("change", event)
        }
    }
  };
</script>

<template>
    <select @change="emitChange">
      <option v-for="choice in store.choices" :key="choice.id" :value="choice.archetype_name">
        {{ choice.archetype_name }}
      </option>
    </select>
  </template>
  
  
  <style lang="scss" scoped>
  select {
    width: auto;
    margin-left: 50px;
    margin-bottom: 30px;
  }
  </style>
  