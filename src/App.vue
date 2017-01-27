<template>
  <div id="app">
    <app-abilities></app-abilities>
  </div>
</template>

<script>
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
    background-color: #222;
  }
</style>
