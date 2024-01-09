<!-- <script>
import { store } from '../store'
export default{
    name: 'AppChoice',
    data() {
        return {
            store,
        }
    }

}
</script>

<template>
<select>
    <option v-for="choice in store.choices" :key="choice.id" value="choice">
    </option>
</select>
</template>

<style lang="scss" scoped>
select {
    width: 100px;
}
</style> -->

<script>
  import { store } from '../store';
  
  export default {
    name: 'AppChoice',
    data() {
      return {
        store: store,
      };
    },
  };
</script>

<template>
    <select>
      <option v-for="choice in store.choices" :key="choice.id" :value="choice">
        {{ choice.archetype_name }}
      </option>
    </select>
  </template>
  
  
  
  <style lang="scss" scoped>
  select {
    width: auto;
  }
  </style>
  