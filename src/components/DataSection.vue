<template>
  <div class="TitleLarge">
    <h2>The Size of the Problem.</h2>
  </div>
  <div class="filters">
    <el-checkbox-group :model-value="checkedUnits" @update:model-value="$emit('update:checkedUnits', $event)">
      <el-checkbox
        @mousedown="$emit('removeOtherUnit')"
        v-for="unit in units"
        :label="unit"
        :key="unit"
        >{{ unit }}</el-checkbox
      >
    </el-checkbox-group>
  </div>
  <!-- Viz1 -->
  <div class="section">
    <VueOnlyTest
      :Final="filteredFinal"
      :sortedBasin="sortedBasin"
      :FinalByBasin="FinalByBasin"
      :FinalByBasin2="FinalByBasin2"
      :checkedUnits="checkedUnits"
      :listofCauses="listOfCauses"
      :fromChild="fromChild"
      v-on:hoverMain="$emit('hoverMain', $event)"
    />
  </div>
  <!--  -->
  <div class="map1">
    <h1>Over 40 Unique Causes of Impairment in 20 Years.</h1>
    <div class="curved-div2">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#a89d99"
          fill-opacity="1"
          d="M0,224L60,213.3C120,203,240,181,360,154.7C480,128,600,96,720,112C840,128,960,192,1080,208C1200,224,1320,192,1380,176L1440,160L1440,0L1380,0C1320,0,1200,0,1080,0C960,0,840,0,720,0C600,0,480,0,360,0C240,0,120,0,60,0L0,0Z"
        ></path>
      </svg>
      <div class="spacer"></div>
    </div>
    <div class="curved-div">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#a89d99"
          fill-opacity="1"
          d="M0,96L60,85.3C120,75,240,53,360,69.3C480,85,600,139,720,165.3C840,192,960,192,1080,176C1200,160,1320,128,1380,112L1440,96L1440,320L1380,320C1320,320,1200,320,1080,320C960,320,840,320,720,320C600,320,480,320,360,320C240,320,120,320,60,320L0,320Z"
        ></path>
      </svg>
      <div class="spacer"></div>
    </div>
  </div>
</template>

<script>
import VueOnlyTest from "./VueOnlyTest.vue";

export default {
  name: "DataSection",
  components: {
    VueOnlyTest,
  },
  props: {
    checkedUnits: Array,
    units: Array,
    filteredFinal: Array,
    sortedBasin: Array,
    FinalByBasin: Map,
    FinalByBasin2: Map,
    listOfCauses: Array,
    fromChild: String,
  },
};
</script>

<style scoped>
.TitleLarge {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 2em;
  background-image: linear-gradient(rgba(23, 99, 143, 0.267), white 85%);
  height: 25vh;
}
.TitleLarge > h2 {
  margin-top: 8%;
  margin-left: 25vw;
  text-align: left;
}
.filters {
  position: relative;
  text-align: center;
  margin-right: 55px;
  margin-bottom: -32px;
  margin-left: 550px;
}
.section {
  display: block;
}
.map1 {
  display: grid;
  position: relative;
  z-index: -1;
  /* position: sticky was overriding relative locally */
  margin-top: 15%;
  margin-bottom: 25%;
  width: 100%;
  background-size: 100% 80%;
  height: 50vh;
  opacity: 1;
  background-repeat: no-repeat;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px 100px 100px auto;
}
.map1 h1 {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: span 2;
  font-size: 3em;
  z-index: 1;
  margin-top: 15%;
  margin-right: 10%;
  margin-left: 15%;
}
.map1 .curved-div {
  position: relative;
  grid-column-start: 1;
  grid-column-end: 6;
  grid-row-start: 5;
  grid-row-end: 5;
  margin-top: -2%;
}
.map1 .curved-div2 {
  position: relative;
  grid-column-start: 1;
  grid-column-end: 6;
  grid-row-start: 1;
  grid-row-end: 1;
  margin-top: -10%;
}
.curved-div, .curved-div2 {
  position: block;
  height: 55vh;
  width: 100%;
}
.curved-div svg, .curved-div2 svg {
  width: 100%;
  height: auto;
  text-align: top;
  margin-top: 2%;
}
.spacer {
  display: block;
  height: 2vh;
  width: 100%;
}
</style>
