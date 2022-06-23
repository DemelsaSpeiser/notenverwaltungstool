<template>
  <div class="home">
    <h1>Notenverwaltung</h1>
    <table>
      <tr>
        <th>Fach</th>
        <th>Noten eingabe</th>
        <th>Durchschnitt</th>
        <th></th>
      </tr>
      <tr>
        <th>M306</th>
        <td><input @keyup.enter="add306" v-model="new306" placeholder="Note" type="number"></td>
        <td>{{ round(avg306, 0.5) }}</td>
        <td v-for="item in m306" >{{ precise_round(item) }}</td><!-- precise_round(item,2)-->
      </tr>
      <tr>
        <th>M151</th>
        <td><input @keyup.enter="add151" v-model="new151" placeholder="Note" type="number"></td>
        <td>{{ round(avg151, 0.5)}}</td>
        <td v-for="item in m151">{{ precise_round(item) }}</td>
      </tr>
      <tr>
        <th>M152</th>
        <td><input @keyup.enter="add152" v-model="new152" placeholder="Note" type="number"></td>
        <td>{{ round(avg152, 0.5)}}</td>
        <td v-for="item in m152">{{ precise_round(item) }}</td>
      </tr>
      <tr>
        <th>M153</th>
        <td><input @keyup.enter="add153" v-model="new153" placeholder="Note" type="number"></td>
        <td>{{ round(avg153, 0.5)}}</td>
        <td v-for="item in m153">{{ precise_round(item) }}</td>
      </tr>
      <tr>
        <th>ABU</th>
        <td><input @keyup.enter="addABU" v-model="newABU" placeholder="Note" type="number"></td>
        <td>{{ round(avgABU, 0.5)}}</td>
        <td v-for="item in ABU">{{ precise_round(item) }}</td>
      </tr>
      <tr>
        <th>NW</th>
        <td><input @keyup.enter="addNW" v-model="newNW" placeholder="Note" type="number"></td>
        <td>{{ round(avgNW, 0.5)}}</td>
        <td v-for="item in NW">{{ precise_round(item) }}</td>
      </tr>
      <tr>
        <th>RW</th>
        <td><input @keyup.enter="addRW" v-model="newRW" placeholder="Note" type="number"></td>
        <td>{{ round(avgRW, 0.5)}}</td>
        <td v-for="item in RW">{{ precise_round(item) }}</td>
      </tr>
      <tr>
        <th>Sport</th>
        <td><input @keyup.enter="addSport" v-model="newSport" placeholder="Note" type="number"></td>
        <td>{{ round(avgSport, 0.5)}}</td>
        <td v-for="item in Sport">{{ precise_round(item) }}</td>
      </tr>
      <tr>
        <th>Gesamt</th>
        <td></td>
        <td></td>
        <td></td>
      </tr>
    </table>
  </div>
</template>

<script>
import { EMPTY_ARR } from '@vue/shared';
import { computed, ref } from 'vue';
export default {
  name: 'HomeView',
  setup: () =>{

  function round(value, step) {
    step || (step = 1.0);
    var inv = 1.0 / step;
    return Math.round(value * inv) / inv;
  }

  function precise_round(value) {
    return Math.round(value * 100) / 100;
  }
    // Modul 306
    const new306 = ref("") // Eingabe Note
    const m306 = ref([]) // Ausgabe
    let count306 = ref(0) // Zähler
    let total306 = ref(0) // Total

    // Modul 151
    const new151 = ref("")
    const m151 = ref([])
    let count151 = ref(0)
    let total151 = ref(0)

    // Modul 152
    const new152 = ref("")
    const m152 = ref([])
    let count152 = ref(0)
    let total152 = ref(0)

    // Modul 153
    const new153 = ref("")
    const m153 = ref([])
    let count153 = ref(0)
    let total153 = ref(0)

    // ABU
    const newABU = ref("")
    const ABU = ref([])
    let countABU = ref(0)
    let totalABU = ref(0)

    // Naturwissenschaft
    const newNW = ref("")
    const NW = ref([])
    let countNW = ref(0)
    let totalNW = ref(0)

    // Rechnungswesen
    const newRW = ref("")
    const RW = ref([])
    let countRW = ref(0)
    let totalRW = ref(0)

    // Sport
    const newSport = ref("")
    const Sport = ref([])
    let countSport = ref(0)
    let totalSport = ref(0)

    // Gesamt
    const newGesamt = ref("")
    const Gesamt = ref([])
    let countGesamt = ref(0)
    let totalGesamt = ref(0)



    function add306(){
      m306.value.push(new306.value);
      count306.value = count306.value + 1;
      total306.value = total306.value + parseFloat(new306.value);
      new306.value = "";
    }
    // Durchschnitt
    const avg306 = computed(function() {
      if (count306.value === 0) {
        return 0
      }
      console.log(count306.value);
      console.log(total306.value);
      return total306.value / count306.value
    })

    function add151(){
      m151.value.push(new151.value);
      count151.value = count151.value + 1;
      total151.value = total151.value + parseFloat(new151.value);
      new151.value = "";
    }
    // Durchschnitt
    const avg151 = computed(function(){
      if(count151.value === 0){
        return 0
      }
      console.log(count151.value);
      console.log(total151.value);
      return total151.value / count151.value
    })

      function add152(){
      m152.value.push(new152.value);
      count152.value = count152.value + 1;
      total152.value = total152.value + parseFloat(new152.value);
      new152.value = "";
    }
    // Durchschnitt
    const avg152 = computed(function(){
      if(count152.value === 0){
        return 0
      }
      console.log(count152.value);
      console.log(total152.value);
      return total152.value / count152.value
    })

      function add153(){
      m153.value.push(new153.value);
      count153.value = count153.value + 1;
      total153.value = total153.value + parseFloat(new153.value);
      new153.value = "";
    }
    // Durchschnitt
    const avg153 = computed(function(){
      if(count153.value === 0){
        return 0
      }
      console.log(count153.value);
      console.log(total153.value);
      return total153.value / count153.value
    })

        function addABU(){
      ABU.value.push(newABU.value);
      countABU.value = countABU.value + 1;
      totalABU.value = totalABU.value + parseFloat(newABU.value);
      newABU.value = "";
    }
    // Durchschnitt
    const avgABU = computed(function(){
      if(countABU.value === 0){
        return 0
      }
      console.log(countABU.value);
      console.log(totalABU.value);
      return totalABU.value / countABU.value
    })

    function addNW(){
      NW.value.push(newNW.value);
      countNW.value = countNW.value + 1;
      totalNW.value = totalNW.value + parseFloat(newNW.value);
      newNW.value = "";
    }
    // Durchschnitt
    const avgNW = computed(function(){
      if(countNW.value === 0){
        return 0
      }
      console.log(countNW.value);
      console.log(totalNW.value);
      return totalNW.value / countNW.value
    })

    function addRW(){
      mRW.value.push(newRW.value);
      countRW.value = countRW.value + 1;
      totalRW.value = totalRW.value + parseFloat(newRW.value);
      newRW.value = "";
    }
    // Durchschnitt
    const avgRW = computed(function(){
      if(countRW.value === 0){
        return 0
      }
      console.log(countRW.value);
      console.log(totalRW.value);
      return totalRW.value / countRW.value
    })

    function addSport(){
      Sport.value.push(newSport.value);
      countSport.value = countSport.value + 1;
      totalSport.value = totalSport.value + parseFloat(newSport.value);
      newSport.value = "";
    }
    // Durchschnitt
    const avgSport = computed(function(){
      if(countSport.value === 0){
        return 0
      }
      console.log(countSport.value);
      console.log(totalSport.value);
      return totalSport.value / countSport.value
    })

    function avgGesamt(){
      if(avg151 != 0){
        countAVG.value = countAVG.value + 1;
      }
      if(avg152 != 0){
        countAVG.value = countAVG.value + 1;
      }
      if(avg153 != 0){
        countAVG.value = countAVG.value + 1;
      }
    }

    return{
      add306,
      new306,
      m306,
      avg306,
      add151,
      new151,
      m151,
      avg151,
      add152,
      new152,
      m152,
      avg152,
      add153,
      new153,
      m153,
      avg153,
      addABU,
      newABU,
      ABU,
      avgABU,
      addNW,
      newNW,
      NW,
      avgNW,
      addRW,
      newRW,
      RW,
      avgRW,
      addSport,
      newSport,
      Sport,
      avgSport,
      precise_round,
      round,
    }
  }
}
</script>

<style lang="scss">
.home{
  margin: 5px 10px;
  h1{
    text-align: center;
  }
  table{
    margin: 0 auto;
    border-collapse: collapse;
    border: 1px solid #000000;
    tr, th, td{
      border: 1px solid #000000;
    }
  }
}
</style>
