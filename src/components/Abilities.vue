<template>
  <div class="row container">
    <div >
       <div class="ability col-md-4 col-md-offset-1"> 
         <table class="table table-hover">
           <thead>
              <tr>
                <th>Ability</th>
                <th>Score</th>
              </tr>
           </thead>
           <tbody>
             <tr v-for="(ability, index) in abilities">
               <td>{{ index }}: </td> <td>{{ ability }}</td> <td v-if="adjustAbility">
                 <div class="dropdown">
                  <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown">Adjust</button>
                  <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                      <option v-for="(cost, index) in abilityCost" class="dropdown-item" >{{ cost }}</option>
                  </div>
                  </div>
               </td>
             </tr>
           </tbody>
         </table>
         <div class="dropdown">
  <button id="dLabel" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Dropdown trigger
    <span class="caret"></span>
  </button>
  <ul class="dropdown-menu" aria-labelledby="dLabel">
    ...
  </ul>
</div>
       </div>
       <div class="col-md-3"></div>
       <div class="col-md-3"></div>
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
        adjustAbility: true
      }
    },
    methods: {
    }
  }
</script>

<style scoped>
    .container {
        border: 1px solid black;
    }
</style>