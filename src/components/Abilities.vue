<template>
  <div class="row">
    <div v-for="ability in abilityText">
       <div class="ability col-md-4 col-md-offset-1"> {{ ability }}</div>
       <div class="score col-md-3">score</div>
       <div class="score col-md-3">cost</div>
     </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        abilityText: ['Str', 'Dex', 'Con', 'Int', 'Wis', 'Chr'],
        strScore: 8,
        dexScore: 8,
        conScore: 8,
        intScore: 8,
        wisScore: 8,
        chrScore: 8
      }
    }
  }
</script>

<style scoped>

</style>