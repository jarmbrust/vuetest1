<template>
  <div class="race-description-container">
    <div>
      {{ selectedRace }}
      Frequency: {{ descriptions['Freq']}}
      {{ descriptions[selected] }}
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        descriptions: {
          'Default': [{'Freq': ''}, {'Desc': ''}],
          'Nokoyan Human': [{'Freq': 'Common'}, {'Desc': 'These humans have fair skin and a variety of hair colors.  Their ancestors came from across the eastern sea'}],
          'Sarruthan Human': [{'Freq': 'Uncommon'}, {'Desc': 'These humans have medium to dark skin tones and usually straight dark hair. Their ancestors came from southern parts of the contenent.'}],
          'High Elf': [{'Freq': 'Uncommon'}, {'Desc': 'TBD'}],
          'Wood Elf': [{'Freq': 'Rare'}, {'Desc': 'TBD'}],
          'Drow Elf': [{'Freq': 'Very Rare'}, {'Desc': 'TBD'}],
          'Hill Dwarf': [{'Freq': 'Common'}, {'Desc': 'TBD'}],
          'Mountain Dwarf': [{'Freq': 'Rare'}, {'Desc': 'TBD'}],
          'Rock Gnome': [{'Freq': 'Common'}, {'Desc': 'TBD'}],
          'Forest Gnome': [{'Freq': 'Very Rare'}, {'Desc': 'TBD'}],
          'Lightfoot Halfling': [{'Freq': 'Uncommon'}, {'Desc': 'TBD'}],
          'Stout Halfling': [{'Freq': 'Rare'}, {'Desc': 'TBD'}],
          'Abyssal Tiefling': [{'Freq': 'Uncommon'}, {'Desc': 'TBD'}],
          'Infernal Tiefling': [{'Freq': 'Uncommon'}, {'Desc': 'TBD'}],
          'Half-Orc': [{'Freq': 'Uncommon'}, {'Desc': 'TBD'}],
          'Half-Elf': [{'Freq': 'Rare'}, {'Desc': 'TBD'}],
          'Dragonborn': [{'Freq': 'Rare'}, {'Desc': 'TBD'}]
        },
        selected: ''
      }
    },
    methods: {
    },
    computed: {
      selectedRace () {
        console.log('test', this.$store.state.selectedRace)
        this.selected = this.$store.state.selectedRace
        return this.$store.state.selectedRace
      }
    }
  }
</script>

<style scoped>
  .race-description-container {
    color: #EEE;
  }
</style>
