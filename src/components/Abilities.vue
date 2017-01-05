<template>
  <div class="row container">
    <div v-for="(ability, index) in abilities">
       <div class="ability col-md-4 col-md-offset-1"> {{ index }}: <span class="score"> {{ ability }} </span></div>
       <div class="col-md-3">score</div>
       <div class="col-md-3">cost</div>
     </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        abilities: {
          'Str': 8,
          'Dex': 8,
          'Con': 8,
          'Int': 8,
          'Wis': 8,
          'Chr': 8
        },
        points: 27
      }
    }
  }
</script>

<style scoped>
    .container {
        border: 1px solid black;
    }
</style>