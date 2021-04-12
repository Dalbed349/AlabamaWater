<template>
  <div class="IntroGlacier">
    <div class="container"></div>
    <div class="bg"></div>
    <div>
      <h1 class="title2">20 years of Water Quality testing in Alabama</h1>
    </div>
    <!-- <img alt="Vue logo" src="./assets/logo.png" />

    <img alt="Vue logo" src="./assets/logo.png" /> -->
    <!-- INTRO   -->
    <div class="Intro">
      <h2>INTRO</h2>
      <p>
        sample text sample text sample text sample text sample text sample text
        sample text sample text sample text sample text sample text sample text
        sample text sample text sample text sample text sample text sample text
        sample text sample text sample text sample text sample text sample text
        sample text sample text sample text sample text sample text sample text
        sample text sample text sample text sample text sample text sample text
        sample text sample text sample text sample text sample text sample text
      </p>
    </div>

    <!-- FILTERS -->
    <div class="filters">
      <el-checkbox-group v-model="filters">
        <el-checkbox label="2020"></el-checkbox>
        <el-checkbox label="2018"></el-checkbox>
        <el-checkbox label="2016"></el-checkbox>
        <el-checkbox label="2014"></el-checkbox>
        <el-checkbox label="2012"></el-checkbox>
        <el-checkbox label="2010"></el-checkbox>
        <el-checkbox label="2008"></el-checkbox>
        <el-checkbox label="2006"></el-checkbox>
        <el-checkbox label="2004"></el-checkbox>
        <el-checkbox label="2002"></el-checkbox>
        <el-checkbox label="2000"></el-checkbox>
      </el-checkbox-group>
    </div>
    <!--  -->

    <div class="filters">
      <el-checkbox
        :indeterminate="isIndeterminate"
        v-model="checkAll"
        @change="handleCheckAllChange"
        >Check all</el-checkbox
      >
      <div style="margin: 15px 0;"></div>
      <el-checkbox-group
        v-model="checkedUnits"
        @change="handleCheckedUnitsChange"
      >
        <el-checkbox v-for="unit in units" :label="unit" :key="unit">{{
          unit
        }}</el-checkbox>
      </el-checkbox-group>
    </div>

    <!--  -->

    <!-- -->

    <img alt="Vue" src="./assets/riverBasins.png" height="400" contain />
    <div>
      <h2>Understanding the length of the problem {{ scrollTop }}</h2>
    </div>
  </div>
  <!-- <div
    class="section"

  >
  <percentage-details
  
  </div> -->

  <!-- horizontal bar chart  -->
  <div class="section">
    <VueOnlyTest
      :Final="filteredFinal"
      :sortedBasin="sortedBasin"
      :FinalByBasin="FinalByBasin"
      :FinalByBasin2="FinalByBasin2"
      :checkedUnits="checkedUnits"
      :listofCauses="listOfCauses"
    />
  </div>

  <!--  -->
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />

  <!-- SMALL MULTIPLES -->
  <!-- FILTERS -->
  <div class="filters">
    <el-checkbox-group v-model="filters">
      <el-checkbox label="2020"></el-checkbox>
      <el-checkbox label="2018"></el-checkbox>
      <el-checkbox label="2016"></el-checkbox>
      <el-checkbox label="2014"></el-checkbox>
      <el-checkbox label="2012"></el-checkbox>
      <el-checkbox label="2010"></el-checkbox>
      <el-checkbox label="2008"></el-checkbox>
      <el-checkbox label="2006"></el-checkbox>
      <el-checkbox label="2004"></el-checkbox>
      <el-checkbox label="2002"></el-checkbox>
      <el-checkbox label="2000"></el-checkbox>
    </el-checkbox-group>
  </div>

  <!-- -->
  <div class="viz2">
    <!-- listOfBasins key = key -->
    <CauseMultiples
      v-for="key in sortedBasin"
      :key="key"
      :data="filteredSmallMultiples"
      :basin="key[0]"
    >
    </CauseMultiples>
  </div>

  <div class="section">
    <BarChart
      title="Bar Chart Placeholder"
      xKey="name"
      yKey="amount"
      :data="barChartData"
    />
    <!-- <BarChart title="Bar Chart Placeholder" xKey="Causes" yKey="Size" :data="filteredFinal"/> -->
  </div>
  <!--  -->
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- /// -->
  <HelloWorld2 msg="new world" />

  <Modal :scrollPosition="scrollTop"> </Modal>

  <img alt="Vue logo" src="./assets/logo.png" />
</template>

<script>
import BarChart from "./components/BarChart.vue";
import HelloWorld from "./components/HelloWorld.vue";
import VueOnlyTest from "./components/VueOnlyTest.vue";
import HelloWorld2 from "./components/HelloWorld2.vue";
import CauseMultiples from "./components/CauseMultiples.vue";
import Modal from "./components/Modal.vue";
import * as d3 from "d3";
// import PercentageDetails from "./components/PercentageDetails.vue";

const unitOptions = ["miles", "acres"];

export default {
  name: "App",
  data() {
    return {
      scrollTop: 0,
      Final: [],
      filters: [
        "2020",
        "2018",
        "2016",
        "2014",
        "2012",
        "2010",
        "2008",
        "2006",
        "2004",
        "2002",
        "2000",
      ],

      checkAll: false,
      checkedUnits: ["miles"],
      units: unitOptions,
      isIndeterminate: true,

      barChartData: [
        {
          name: "Roses",
          amount: 25,
        },
        {
          name: "Tulips",
          amount: 40,
        },
        {
          name: "Daisies",
          amount: 15,
        },
        {
          name: "Narcissuses",
          amount: 9,
        },
        {
          name: "farcissuses",
          amount: 9,
        },
        {
          name: "harcissuses",
          amount: 9,
        },
      ],
    };
  },

  computed: {
    filteredFinal() {
      if (!this.Final) {
        return null;
      }

      return this.Final.filter(
        (d) =>
          this.filters.includes(d.ReportYear) &&
          this.checkedUnits.includes(d.UnitType)
      );
    },
    FinalByBasin() {
      if (!this.filteredFinal) {
        return new Map();
      } // first key  can chain more , d.key1, d => d.key2, ...)
      let g = d3.rollup(
        this.filteredFinal,
        (values) => d3.sum(values.map((d) => +d["Size"])),
        (d) => d["RiverBasin"]
      );

      return g;
    },
    FinalByBasin2() {
      if (!this.filteredFinal) {
        return new Map();
      } // first key  can chain more , d.key1, d => d.key2, ...)
      let g = d3.rollup(
        this.filteredFinal,
        (values) => d3.sum(values.map((d) => +d["Size"])),
        (d) => d["RiverBasin"],
        (d) => d["Causes"]
      );

      // let t = Array.from(g);
      // let z = t.forEach((element) => Array.from(element[1]));
      // let z = t.forEach((element) => console.log(Array.from(element[1])));
      return g;
      // return g;
    },

    sortedBasin() {
      let g = Array.from(this.FinalByBasin); //.sort((a,b) => d3.ascending(a.value, b.value))

      var f = g.sort(function(a, b) {
        return b[1] - a[1];
      });
      return f;
    },
    sortedFinalByBasin2() {
      let g = Array.from(this.FinalByBasin2);
      var f = g.sort(function(a, b) {
        return b[1] - a[1];
      });
      return f;
    },
    listOfBasins() {
      return Array.from(new Set(this.Final.map((d) => d.RiverBasin)));
    },
    listOfCauses() {
      return Array.from(new Set(this.filteredFinal.map((d) => d.Causes)));
    },
    filteredSmallMultiples() {
      // if (!this.Final) {
      //   return null;
      // }

      return this.Final.filter(
        (d) => this.filters.includes(d.ReportYear) && d.UnitType == "miles"
      );
    },
  },

  components: {
    // PercentageDetails,
    HelloWorld,
    HelloWorld2,
    CauseMultiples,
    VueOnlyTest,
    BarChart,
    Modal,
  },
  mounted() {
    Promise.all([d3.csv("TESTFinalCompiledCSV.csv")]).then((data) => {
      this.Final = data[0];
      // console.log(this.Final);
    }),
      window.addEventListener("scroll", this.onScroll);
  },
  unmounted() {
    window.removeEventListener("scroll", this.onScroll);
  },
  methods: {
    onScroll(/*event*/) {
      // console.log(window.scrollY);
      this.scrollTop = window.scrollY;
    },
    handleCheckAllChange(val) {
      this.checkedUnits = val ? unitOptions : [];
      this.isIndeterminate = false;
    },
    handleCheckeUnitsChange(value) {
      let checkedCount = value.length;
      this.checkAll = checkedCount === this.units.length;
      this.isIndeterminate =
        checkedCount > 0 && checkedCount < this.units.length;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
.Intro {
  position: relative;
  left: 0;
  height: 200px;
  color: white;
  margin-top: 100px;
  margin-left: 20%;
  margin-right: 20%;
  text-shadow: 3px 3px 0 #000, -1px -1px 0 #000, 1px -1px 0 #000,
    -1px 1px 0 #000;
}
.viz2 {
  display: grid;
  grid-template-rows: repeat(4, 1fr);
  grid-template-columns: repeat(2, 1fr);
}
.IntroGlacier {
  /* background-image: url("./assets/glacier.jpg"); */
}
/* .myDiv {
  position: relative;
  z-index: 5;
  height: 250px;
  width: 300px;
  color: #000;
  font-size: 400%;
  padding: 20px;
} */
.title2 {
  color: white;
  text-shadow: 3px 3px 0 #000, -1px -1px 0 #000, 1px -1px 0 #000,
    -1px 1px 0 #000;
}
.IntroGlacier .bg {
  position: absolute;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: url("./assets/glacier.jpg") center center;
  opacity: 0.7;
  width: 100%;
  height: 110%;
}
</style>
