<template>
  <div>
    <button class="btn btn-secondary dropdown-toggle race" type="button" id="dropdownMenuButton" data-toggle="dropdown">Race <span class="caret"></span></button>
    <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
      <option v-for="race in races" class="dropdown-item" @click="selectRace(race)"> {{ race }}</option>
    </div>
    <div v-if="selectedRace === 'Elf' || selectedRace === 'Dwarf' || selectedRace === 'Gnome' || selectedRace === 'Halfling' || selectedRace === 'Human' || selectedRace === 'Tiefling'">
      <button class="btn btn-secondary dropdown-toggle sub-race" type="button" id="dropdownMenuButtonSub" data-toggle="dropdown">SubRace <span class="caret"></span></button>
      <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
        <option v-for="subRace in subRaces[selectedRace]" class="dropdown-item" @click="selectRace(subRace)"> {{ subRace }}</option>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        races: [
          'Human', 'Elf', 'Dwarf', 'Gnome', 'Halfling', 'Half-Orc', 'Half-Elf', 'Tiefling'
        ],
        subRaces: {
          'Human': ['Nokoyan Human', 'Sarruth Human'],
          'Elf': ['High Elf', 'Wood Elf', 'Drow Elf'],
          'Dwarf': ['Hill Dwarf', 'Mountain Dwarf'],
          'Gnome': ['Rock Gnome', 'Forest Gnome'],
          'Halfling': ['Halfling, Lightfoot', 'Halfling, Stout'],
          'Tiefling': ['Abyssal Tiefling', 'Infernal Tiefling']
        },
        selectedRace: ''
      }
    },
    methods: {
      selectRace (race) {
        console.log(race + ' in component')
        this.selectedRace = race
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