<template>
  <div class="row container">
    <div  class="ability col-md-4 col-md-offset-1">
       <div> 
         <table class="table table-hover">
           <thead>
              <tr>
                <th>Ability</th>
                <th>Total</th>
                <th>Score</th>
                <th>Race<br>Bonus</th>
              </tr>
           </thead>
           <tbody>
             <tr v-for="(ability, index) in abilities">
               <td>{{ index }}: </td> <td class="total-score">{{ Number(ability) + Number(raceBonus[index]) }}</td> <td class="score">{{ ability }}</td> <td class="race-bonus">{{ raceBonus[index] }}</td> <td v-if="adjustAbility">
                 <div class="dropdown">
                  <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown">Adjust <span class="caret"></span></button>
                  <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                      <option v-for="(cost, value) in abilityCost" class="dropdown-item" @click="ability = selected(value, index)">{{ value }} -- (Cost: {{ cost }})</option>
                  </div>
                </div>
               </td>
             </tr>
           </tbody>
         </table>
         <div>Points: <span class="total-points">{{ this.points }} </span>
          <button class="btn btn-primary reset" type="button" @click="resetStats">Reset Stats</button>
         </div>
        </div>
       </div>
       <div class="col-md-3">
         <app-race @selectedRace="selectedRace"></app-race>
         <div class="selected-race"> {{ race }}</div>
       </div>
       <div class="col-md-3"></div>
     </div>
  </div>
</template>

<script>
  import Race from './Race.vue'

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
        raceBonus: {
          'Str': 0,
          'Dex': 0,
          'Con': 0,
          'Int': 0,
          'Wis': 0,
          'Chr': 0
        },
        points: 27,
        abilityCost: {
          8: 0,
          9: 1,
          10: 2,
          11: 3,
          12: 4,
          13: 5,
          14: 7,
          15: 9
        },
        adjustAbility: true,
        race: ''
      }
    },
    methods: {
      selected (value, index) {
        this.adjustPoints(value, index)
        this.abilities[index] = value
      },
      adjustPoints (value, index) {
        let currentValue = this.abilityCost[this.abilities[index]]
        let valueAdj = this.abilityCost[value]
        let pointCost = currentValue - valueAdj
        this.points += pointCost
      },
      resetStats () {
        for (var key in this.abilities) {
          this.abilities[key] = 8
        }
        this.points = 27
      },
      selectedRace (race, bonus) {
        this.race = race
        for (var stat in this.raceBonus) {
          this.raceBonus[stat] = bonus[stat]
        }
      }
    },
    components: {
      appRace: Race
    }
  }
</script>

<style scoped>
    .container {
        /*border: 1px solid black;*/
    }
    .dropdown-item {
      padding-left: 10px;
      cursor: pointer;
    }
    .dropdown-item:hover {
      background-color: #ccc;
    }
    .total-points {
      padding: 10px;
      font-size: 18px;
    }
    .reset {
      margin: 2px;
    }
    .selected-race {
      padding: 10px;
    }
    .total-score {
      font-weight: bold;
      font-size: 18px;
    }
</style>