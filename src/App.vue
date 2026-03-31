<template>
  <div id="app-container">
    <HeroSection />
    
    <HabitatSection />
    
    <HistorySection />

    <MapBasinSection />

    <DataSection 
      :checkedUnits="checkedUnits"
      :units="units"
      :filteredFinal="filteredFinal"
      :sortedBasin="sortedBasin"
      :FinalByBasin="FinalByBasin"
      :FinalByBasin2="FinalByBasin2"
      :listOfCauses="listOfCauses"
      :fromChild="fromChild"
      @update:checkedUnits="checkedUnits = $event"
      @removeOtherUnit="removeOtherUnit"
      @hoverMain="onChildClick2"
    />

    <div class="map1">
      <h1>Over 40 Unique Causes of Impairment in 20 Years.</h1>
      <div class="curved-div2">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
          <path fill="#a89d99" fill-opacity="1" d="M0,224L60,213.3C120,203,240,181,360,154.7C480,128,600,96,720,112C840,128,960,192,1080,208C1200,224,1320,192,1380,176L1440,160L1440,0L1380,0C1320,0,1200,0,1080,0C960,0,840,0,720,0C600,0,480,0,360,0C240,0,120,0,60,0L0,0Z"></path>
        </svg>
        <div class="spacer"></div>
      </div>
      <div class="curved-div">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
          <path fill="#a89d99" fill-opacity="1" d="M0,96L60,85.3C120,75,240,53,360,69.3C480,85,600,139,720,165.3C840,192,960,192,1080,176C1200,160,1320,128,1380,112L1440,96L1440,320L1380,320C1320,320,1200,320,1080,320C960,320,840,320,720,320C600,320,480,320,360,320C240,320,120,320,60,320L0,320Z"></path>
        </svg>
        <div class="spacer"></div>
      </div>
    </div>

    <MultiplesSection 
      :checkedUnits="checkedUnits"
      :units="units"
      :filteredSmallMultiples="filteredSmallMultiples"
      :hoverSecondVis="hoverSecondVis"
      :hoverSecondVisCause="hoverSecondVisCause"
      :counter="counter"
      :sortedBasin="sortedBasin"
      @update:checkedUnits="checkedUnits = $event"
      @removeOtherUnit="removeOtherUnit"
      @increment="incrementCounter"
      @decrease="decreaseCounter"
      @hoverSecondVis="onChildClick3"
      @hoverSecondVisCause="onChildClick4"
    />

    <FooterSection />

    <Modal
      v-on:increment="incrementCounter"
      v-on:decrease="decreaseCounter"
      :scrollPosition="scrollTop"
      :counter="counter"
      :modalYpos="modalYpos"
      :modalYposEnd="modalYposEnd"
      :hoverCentral="hoverCentral"
      :sortedBasin="sortedBasin"
      :sortedBasinOnlyNames="sortedBasinOnlyNames"
    />
    
    <ModalLegend
      v-on:childToParent="onChildClick"
      :scrollPosition="scrollTop"
      :counter="counter"
      :modalYpos="modalYpos"
      :modalYposEnd="modalYposEnd"
      :listofCauses="listOfCauses"
      :listOfCausesFiltered="listOfCausesFiltered"
    />
  </div>
</template>

<script>
import * as d3 from "d3";
import HeroSection from "./components/HeroSection.vue";
import HabitatSection from "./components/HabitatSection.vue";
import HistorySection from "./components/HistorySection.vue";
import MapBasinSection from "./components/MapBasinSection.vue";
import DataSection from "./components/DataSection.vue";
import MultiplesSection from "./components/MultiplesSection.vue";
import FooterSection from "./components/FooterSection.vue";
import Modal from "./components/Modal.vue";
import ModalLegend from "./components/ModalLegend.vue";

const unitOptions = ["miles", "acres"];

function uniqueSum(data) {
  let alreadySeen = {};
  let sum = 0;
  for (let i = 0; i < data.length; i++) {
    if (!alreadySeen[data[i].AssessmentUnitID]) {
      sum = sum + +data[i]["Size"];
      alreadySeen[data[i].AssessmentUnitID] = true;
    }
  }
  return sum;
}

export default {
  name: "App",
  components: {
    HeroSection,
    HabitatSection,
    HistorySection,
    MapBasinSection,
    DataSection,
    MultiplesSection,
    FooterSection,
    Modal,
    ModalLegend,
  },
  data() {
    return {
      scrollTop: 0,
      Final: [],
      modalYpos: 0,
      hoverSecondVisCause: null,
      modalYposEnd: 0,
      filters: [
        "2000", "2002", "2004", "2006", "2008",
        "2010", "2012", "2014", "2016", "2018", "2020",
      ],
      counter: 0,
      hoverCentral: "",
      hoverSecondVis: null,
      fromChild: "",
      checkedUnits: ["miles"],
      units: unitOptions,
    };
  },
  computed: {
    filteredFinal() {
      if (!this.Final || this.Final.length === 0) return [];
      return this.Final.filter(
        (d) =>
          this.filters[this.counter].includes(d.ReportYear) &&
          this.checkedUnits.includes(d.UnitType)
      );
    },
    FinalByBasin() {
      if (!this.filteredFinal || this.filteredFinal.length === 0) return new Map();
      return d3.rollup(
        this.filteredFinal,
        (values) => d3.sum(values.map((d) => +d["Size"])),
        (d) => d["RiverBasin"]
      );
    },
    FinalByBasin2() {
      if (!this.filteredFinal || this.filteredFinal.length === 0) return new Map();
      return d3.rollup(
        this.filteredFinal,
        (values) => d3.sum(values.map((d) => +d["Size"])),
        (d) => d["RiverBasin"],
        (d) => d["Causes"]
      );
    },
    sortedBasin() {
      let g = Array.from(this.FinalByBasin);
      return g.sort((a, b) => b[1] - a[1]);
    },
    sortedBasinOnlyNames() {
      return this.sortedBasin.map(b => b[0]);
    },
    listOfCauses() {
      return Array.from(new Set(this.Final.map((d) => d.Causes)));
    },
    listOfCausesFiltered() {
      return Array.from(
        new Set(this.filteredFinal.map((d) => d.Causes))
      ).sort();
    },
    filteredSmallMultiples() {
      return this.filteredFinal;
    },
  },
  mounted() {
    Promise.all([d3.csv("./TESTFinalCompiledCSV2.csv")]).then((data) => {
      this.Final = data[0];
    });
    window.addEventListener("scroll", this.onScroll);
    
    // Modal positioning timeout allows DOM render
    setTimeout(() => {
      const x = document.getElementsByClassName("TitleLarge")[0];
      if (x) this.modalYpos = x.getBoundingClientRect().y;
      
      const x2 = document.getElementsByClassName("map1")[0];
      if (x2) this.modalYposEnd = x2.getBoundingClientRect().bottom;
    }, 100);
  },
  unmounted() {
    window.removeEventListener("scroll", this.onScroll);
  },
  methods: {
    incrementCounter() {
      if (this.counter < 10) this.counter++;
    },
    decreaseCounter() {
      if (this.counter > 0) this.counter--;
    },
    onChildClick(value) {
      this.fromChild = value;
    },
    onChildClick2(value) {
      this.hoverCentral = value;
    },
    onChildClick3(value) {
      this.hoverSecondVis = value;
    },
    onChildClick4(value) {
      this.hoverSecondVisCause = value;
    },
    onScroll() {
      this.scrollTop = window.scrollY;
    },
    removeOtherUnit() {
      // Logic replicated exactly from original code
      if (this.checkedUnits.includes("miles")) {
        this.checkedUnits.splice(this.checkedUnits.indexOf("miles"), 1);
      }
      if (this.checkedUnits.includes("acres")) {
        this.checkedUnits.splice(this.checkedUnits.indexOf("acres"), 1);
      }
    },
  },
};
</script>

<style>
/* Global Styles remain here, scoped styles went into components */
#app {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
  margin-left: -10px;
  margin-right: -10px;
  margin-top: -2%;
  display: flex;
  flex-direction: column;
}

/* Map1 styles kept global because App.vue still hosts this intermediate map section */
.map1 {
  display: grid;
  position: relative;
  z-index: -1;
  margin-top: 15%;
  margin-bottom: 25%;
  width: 100%;
  background-size: 100% 80%;
  height: 50vh;
  opacity: 1;
  background-repeat: no-repeat;
  grid-template-columns: minmax(5px, 40px) minmax(5px, 50px) auto minmax(5px, 50px) minmax(5px, 40px);
  grid-template-rows: 25% 100px 100px 100px auto;
}
.map1 h1 {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: span 2;
  font-size: clamp(2em, 5vw, 3em);
  z-index: 1;
  margin-top: 15%;
  margin-right: 5%;
  margin-left: 5%;
}
@media (min-width: 1024px) {
  .map1 h1 {
    margin-right: 10%;
    margin-left: 15%;
  }
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
