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
          'Human', 'Elf', 'Dwarf', 'Gnome', 'Halfling', 'Half-Orc', 'Half-Elf', 'Tiefling', 'Dragonborn'
        ],
        subRaces: {
          'Human': ['Nokoyan Human', 'Sarruth Human'],
          'Elf': ['High Elf', 'Wood Elf', 'Drow Elf'],
          'Dwarf': ['Hill Dwarf', 'Mountain Dwarf'],
          'Gnome': ['Rock Gnome', 'Forest Gnome'],
          'Halfling': ['Lightfoot Halfling', 'Stout Halfling'],
          'Tiefling': ['Abyssal Tiefling', 'Infernal Tiefling']
        },
        raceBonus: {
          'Default': {'Str': 0, 'Dex': 0, 'Con': 0, 'Int': 0, 'Wis': 0, 'Chr': 0},
          'Nokoyan Human': {'Str': 1, 'Dex': 1, 'Con': 1, 'Int': 1, 'Wis': 1, 'Chr': 1},
          'Sarruth Human': {'Str': 1, 'Dex': 1, 'Con': 1, 'Int': 1, 'Wis': 1, 'Chr': 1},
          'High Elf': {'Str': 0, 'Dex': 2, 'Con': 0, 'Int': 1, 'Wis': 0, 'Chr': 0},
          'Wood Elf': {'Str': 0, 'Dex': 2, 'Con': 0, 'Int': 0, 'Wis': 1, 'Chr': 0},
          'Drow Elf': {'Str': 0, 'Dex': 2, 'Con': 0, 'Int': 0, 'Wis': 0, 'Chr': 1},
          'Hill Dwarf': {'Str': 0, 'Dex': 0, 'Con': 2, 'Int': 0, 'Wis': 1, 'Chr': 0},
          'Mountain Dwarf': {'Str': 2, 'Dex': 0, 'Con': 2, 'Int': 0, 'Wis': 0, 'Chr': 0},
          'Rock Gnome': {'Str': 0, 'Dex': 0, 'Con': 1, 'Int': 2, 'Wis': 0, 'Chr': 0},
          'Forest Gnome': {'Str': 0, 'Dex': 1, 'Con': 0, 'Int': 2, 'Wis': 0, 'Chr': 0},
          'Lightfoot Halfling': {'Str': 0, 'Dex': 2, 'Con': 0, 'Int': 0, 'Wis': 0, 'Chr': 1},
          'Stout Halfling': {'Str': 0, 'Dex': 2, 'Con': 1, 'Int': 0, 'Wis': 0, 'Chr': 0},
          'Abyssal Tiefling': {'Str': 0, 'Dex': 0, 'Con': 1, 'Int': 0, 'Wis': 0, 'Chr': 2},
          'Infernal Tiefling': {'Str': 0, 'Dex': 0, 'Con': 0, 'Int': 1, 'Wis': 0, 'Chr': 2},
          'Half-Orc': {'Str': 2, 'Dex': 0, 'Con': 1, 'Int': 0, 'Wis': 0, 'Chr': 0},
          'Half-Elf': {'Str': 0, 'Dex': 0, 'Con': 0, 'Int': 0, 'Wis': 0, 'Chr': 2},
          'Dragonborn': {'Str': 2, 'Dex': 0, 'Con': 0, 'Int': 0, 'Wis': 0, 'Chr': 1}
        },
        selectedRace: 'Default'
      }
    },
    methods: {
      selectRace (race) {
        this.selectedRace = race
        let bonusArray = this.raceBonus[this.selectedRace] ? this.raceBonus[this.selectedRace] : this.raceBonus['Default']
        this.$emit('selectedRace', race, bonusArray)
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