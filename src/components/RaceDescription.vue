<template>
  <div class="race-description-container">
    <div>
      {{ race }}
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        descriptions: {
          'Default': {'Description': ''},
          'Nokoyan Human': {'Common': 'These humans have fair skin and a variety of hair colors.  Their ancestors came from across the eastern sea'},
          'Sarruthan Human': {'Uncommon': 'These humans have medium to dark skin tones and usually straight dark hair. Their ancestors came from southern parts of the contenent.'},
          'High Elf': {'Uncommon': 'TBD'},
          'Wood Elf': {'Rare': 'TBD'},
          'Drow Elf': {'Very Rare': 'TBD'},
          'Hill Dwarf': {'Common': 'TBD'},
          'Mountain Dwarf': {'Rare': 'TBD'},
          'Rock Gnome': {'Common': 'TBD'},
          'Forest Gnome': {'Very Rare': 'TBD'},
          'Lightfoot Halfling': {'Uncommon': 'TBD'},
          'Stout Halfling': {'Rare': 'TBD'},
          'Abyssal Tiefling': {'Uncommon': 'TBD'},
          'Infernal Tiefling': {'Uncommon': 'TBD'},
          'Half-Orc': {'Uncommon': 'TBD'},
          'Half-Elf': {'Rare': 'TBD'},
          'Dragonborn': {'Rare': 'TBD'}
        }
      }
    },
    // methods: {
    //   // selectedDescription (race) {
    //   //   console.log('> ', race)
    //   //   return this.descriptions
    //   // },
    //   // selectedRace (race) {
    //   // //  this.race = race
    //   //   console.log('>> ', race)
    //   // }
    // },
    props: ['race']
  }
</script>

<style scoped>
  .race-description-container {
    color: #EEE;
  }
</style>
