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
          'Nokoyan Human': {'Freq': 'Common', 'Desc': 'These humans have fair skin and a variety of hair colors.  Their ancestors came from across the eastern sea around 300 years ago fleeing the Nokoyan Empire, and found the kingdom of Oulan.'},
          'Sarruthan Human': {'Freq': 'Uncommon', 'Desc': 'These humans have medium to dark skin tones and usually straight dark hair. Their ancestors came from southern parts of the contenent and once had a great emipre before it fell to ruins when the misma came.'},
          'High Elf': {'Freq': 'Uncommon', 'Desc': 'Fair skin and light hair colors, and violet to green eyes, these elves are slim and slightly taller than humans. Sophisticated and elegent, they have a reputation for being somewhat aloof.  Their culture generally holds arcane knowledge to be the pinical of study.'},
          'Wood Elf': {'Freq': 'Rare', 'Desc': 'Averaging just over 5\' tall with lean builds, these elves are rare to find in human cities, or any cities. The have tan skin tones and dark or forest colored hair. Most wood elves avoid arcane magics, perferring drudic ways.'},
          'Drow Elf': {'Freq': 'Very Rare', 'Desc': 'With pitch black skin, white to silver hair, and pupiless eyes, the dark elves from the Underdark are shunned and feared by those who know of them.'},
          'Hill Dwarf': {'Freq': 'Common', 'Desc': 'Averaging around 4\' tall and looked to for both their skill in crafts and wisdom on life, these generally gruff but good-natured dwarves come in a variety of skin tones with dark red to black to grey hair.'},
          'Mountain Dwarf': {'Freq': 'Rare', 'Desc': 'Usually not see from the mountain homes unless either on a dire mission or quest, or having been cast out from their people. They are a little taller than their cousins standing about 4\'6", with light skin tones, muscled builds, and heavily tatooed bodies.'},
          'Rock Gnome': {'Freq': 'Common', 'Desc': 'The generally jovial and always curious gnomes are often looked to for their engineering and magical genius, and generally kept away from breakables or anything volitile. They have lighter skin tones and often dye their hair bizzar colors.'},
          'Forest Gnome': {'Freq': 'Very Rare', 'Desc': 'The very rare "fae-gnomes" have brightly colored hair and green, pink, light blue, or other odd-colored skin-tones.  Seldom are they seen outside their forests, and are occasionally hunted by the black-market for the rumored magical properities of their blood or bodyparts.'},
          'Lightfoot Halfling': {'Freq': 'Uncommon', 'Desc': 'Lightfoots generally live a gypsie-like life, where clans and family groups wander from place to place putting on shows or doing odd-jobs. The have a somewhat undeserved reputation for being thieves and vagabonds.'},
          'Stout Halfling': {'Freq': 'Rare', 'Desc': 'Stout halflings come from the same region as Mountain Dwarves, and are about as rare in these parts.  They are surprisingly strong and tough for their size, and are skilled farmers who often trade with their neighbors the dwarves.'},
          'Tiefling': {'Freq': 'Rare', 'Desc': 'Manipulative and cunning, with deep red to purple skin tones, horns, and a tail, tiefling are often shunned and feared where ever they go. The common folk believe that they are the sired offspring of a demon or devil, but some say it is just as likely to be a curse brought about by the miasma. Whichever is the truth, the belief (that many a good tiefling fight against) is that their infernal blood will rule the day.'},
          'Half-Orc': {'Freq': 'Uncommon', 'Desc': 'In the first century that human settlers came these parts, orc raids were common, and half-orcs a brutal product. Now days, most of these strong and tough grey-skinned people are just as likely to be the product of half-orc parents. They have a stigma for being dim-witted and quick to anger, and unfortunately this is often (but not always) the case.'},
          'Half-Elf': {'Freq': 'Rare', 'Desc': 'Looked upon as a pollution of the blood by most high elves, and with curosity among humans (who usually are the ones to raise them), the rare half-elf shares physical trates of both parents. They often have a hard time fitting in to their human families, but generally have strong personalities. Most are believed to be sterile.'},
          'Dragonborn': {'Freq': 'Rare', 'Desc': 'Often viewed with a combination of awe and caution, dragonborn are believed to be decendents of humans who formed a pact with ancient dragons on the lost island of Drakar. They are tall, strong, and fierce.  Often putting great importance on their honor, some will go so far as to fight to the death to protect it.'}
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
