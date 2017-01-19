<template>
  <div>
    <button class="btn btn-secondary dropdown-toggle race" type="button" id="dropdownMenuButton" data-toggle="dropdown">Race <span class="caret"></span></button>
    <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
      <option v-for="race in races" class="dropdown-item" @click="selectRace(race)"> {{ race }}</option>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        races: [
          'human', 'elf', 'dwarf', 'gnome', 'halfling', 'tiefling', 'dragonborn'
        ]
    //    selectRace: 'human'
      }
    },
    methods: {
      selectRace (race) {
        console.log(race + ' in component')
        this.$emit('selectedRace', race)
      }
    }
  }
</script>

<style scoped>
  .dropdown-item {
      padding-left: 10px;
      cursor: pointer;
    }
    .dropdown-item:hover {
      background-color: #ccc;
    }
    .race {
      margin: 2px;
    }
</style>