<template>
  <div class="race-description-container">
    <div>
      <p>
        <span class="heading">Race: </span> <span class="textbody">{{ selectedRace }}</span>
      <br><br>
        <span class="heading">Frequency: </span> <span class="textbody">{{ frequency }}</span>
      <br><br>
        <span class="heading">Description: </span> <span class="textbody">{{ description }}</span>
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        descriptions: {
          'Default': {'Freq': '', 'Desc': ''},
          'Nokoyan Human': {'Freq': 'Common', 'Desc': 'These humans have fair skin and a variety of hair colors.  Their ancestors came from across the eastern sea around 300 years ago to found the kingdom of Osun.'},
          'Sarruthan Human': {'Freq': 'Uncommon', 'Desc': 'These humans have medium to dark skin tones and usually straight dark hair. Their ancestors came from southern parts of the contenent and once had a great emipre before it fell to ruins when the misma came.'},
          'High Elf': {'Freq': 'Uncommon', 'Desc': 'Fair skin and light hair colors, and violet to green eyes, these elves are slim and slightly taller than humans, and have a reputation for being somewhat aloof.  Their culture generally holds arcane knowledge to be the pinical of study.'},
          'Wood Elf': {'Freq': 'Rare', 'Desc': 'Averaging just over 5\' tall with lean builds, these elves are rare to find in human cities, or any cities. The have tan skin tones and dark or forest colored hair. They tend to askque arcane magics, and tend to be powerful rangers and druids.'},
          'Drow Elf': {'Freq': 'Very Rare', 'Desc': 'With pitch black skin, white to silver hair, and pupiless eyes, the dark elves from the Underdark are shunned and feared by those who know of them.'},
          'Hill Dwarf': {'Freq': 'Common', 'Desc': 'Averaging around 4\' tall and looked to for both their skill in crafts and wisdom on life, these dwarves come in a variety of skin tones with dark red to black to grey hair.'},
          'Mountain Dwarf': {'Freq': 'Rare', 'Desc': 'Usually not see from the mountain homes unless under a dire mission, or cast out from their people, these dwarves are a little taller at about 4\'6" with light skin tones, muscled builds, and heavily tatooed bodies.'},
          'Rock Gnome': {'Freq': 'Common', 'Desc': 'The generally jovial and always curious gnomes are often looked to for their engineering and magical genius, and generally kept away from breakables or anything volitile.'},
          'Forest Gnome': {'Freq': 'Very Rare', 'Desc': 'The very rare "fae-gnomes" have brightly colored hair and green to light blue skin-tones.  Seldom are they seen outside their forests, and are occasionally hunted by the black-market for rumored magical properities of their blood or bodyparts.'},
          'Lightfoot Halfling': {'Freq': 'Uncommon', 'Desc': 'Lightfoots generally are a gypsie-like culture that wanders from place to place, puting on shows or doing odd-jobs. The have a somewhat underserved reputation for being thieves and vagabonds.'},
          'Stout Halfling': {'Freq': 'Rare', 'Desc': 'Stout halflings come from the same region as Mountain Dwarves, and are about as rare in these parts.  They are often surprisingly strong for their size and skilled farmers who often trade with their neightbors the dwarves.'},
          'Tiefling': {'Freq': 'Rare', 'Desc': 'Manipulative and cunning, with deep red to purple skin tones, horns, and a tail, they are often shunned and feared where ever they go. The common folk believe that they are the sired offspring of a demon or devil, but some say it is just as likely to be a curse brought about by the miasma. Whichever is the truth, the view often is the apple doesn\'t fall from from the tree.'},
          'Half-Orc': {'Freq': 'Uncommon', 'Desc': 'In the first century that human settlers came these parts, orc raids were common, and half-orcs an brutal product. Now days, most of these strong and tough grey-skinned people are just as likely to be the product of half-orc parents. They have a stigma for being dim-witted and quick to anger, and unfortunately this is often (but not always) the case.'},
          'Half-Elf': {'Freq': 'Rare', 'Desc': 'Looked upon as a pollution of the blood by most high elves, and with curosity among humans (who usually are the ones to raise them), the rare half-elf shares physical trates of both parents. They often have a hard time fitting in to their human families, but generally have strong personalities. Most are believed to be sterile.'},
          'Dragonborn': {'Freq': 'Rare', 'Desc': 'Often rumored to be decendents of humans who formed a pact with ancient dragons on the lost island of Drakar, the Dragonborn are tall, strong, and fierce.  Most put great importance on their honor, some willing to fight to the death against impossible odds to protect it.'}
        },
        selected: '',
        frequency: '',
        description: ''
      }
    },
    methods: {
    },
    computed: {
      selectedRace () {
        this.selected = this.$store.state.selectedRace
        if (this.selected === 'Select "sub-race"' || this.selected == null || this.selected === '') {
          this.frequency = ''
          this.description = ''
          return ''
        }
        this.frequency = this.descriptions[this.selected].Freq
        this.description = this.descriptions[this.selected].Desc
        return this.$store.state.selectedRace
      }
    }
  }
</script>

<style scoped>
  .race-description-container {
    color: #EEE;
    margin: 20px 10px;
  }
  .heading {
    font-size: 16px;
    font-weight: bold;
  }
  .textbody {
    font-size: 17px;
  }
</style>
