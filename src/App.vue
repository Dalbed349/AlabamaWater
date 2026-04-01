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
    // Use window.scrollY to ensure absolute document coordinates even on reload
    setTimeout(() => {
      const x = document.getElementsByClassName("TitleLarge")[0];
      if (x) this.modalYpos = x.getBoundingClientRect().top + window.scrollY;
      
      const x2 = document.getElementsByClassName("section")[0]; // Target the inner DataSection container
      if (x2) this.modalYposEnd = x2.getBoundingClientRect().bottom + window.scrollY;
    }, 1000);
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

</style>
