<template>
  <div id="app">
    <app-abilities></app-abilities>
  </div>
</template>

<script>
// import Hello from './components/Hello'
import Abilities from './components/Abilities.vue'

export default {
  name: 'app',
  components: {
    appAbilities: Abilities
  }
}
</script>

<style>
  body {
    background-color: #EEE;
  }
</style>
