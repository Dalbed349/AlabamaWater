<template>
  <div class="IntroGlacier">
    <!-- <div class="container"></div> -->

    <!-- <div class="bg"></div> -->
    <div class="darken"></div>
    <div class="margins">
      <div>
        <h1 class="title1">
          20 Years of Water
        </h1>
        <h2 class="title2">Visualising Alabama's List of Impaired Waters</h2>
      </div>
      <!-- INTRO   -->
      <div class="Intro">
        <h2>INTRO</h2>
        <p>
          Alabama’s climate and geographic history makes it one of the most
          ecologically diverse states in the United States. At the same time, a
          history of industrial accidents and abuse has led to disasters that
          have harmed everything from ponds to populations of cities to
          coastlines. Since 1998 stricter water monitoring policies have been
          mandated in an attempt to control the human and environmental harm
          caused by pollutants. This project seeks to analyze the progress that
          has been made during the past 20 years of water quality testing. Data
          from the Alabama Department of Environmental Management (ADEM) is used
          to visualize the scope of water contamination in each river basin by
          size, cause, and source.
        </p>
      </div>
    </div>
  </div>
  <!-- -->

  <div class="map">
    <!-- <div class="darken"></div> -->
    <div class="mapImage">
      <div class="transbox">
        <p>
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text
        </p>
      </div>
      <div class="transbox2">
        <p>
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text
        </p>
      </div>
      <img alt="Vue" src="./assets/riverBasins.png" contain />
    </div>
  </div>
  <div class="TitleLarge">
    <h2>The length of the problem...</h2>
    <!-- {{ filters[this.counter] }} -->
  </div>

  <!-- FILTERS -->
  <!-- 
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

  <div class="map">
    <!-- <div class="darken"></div> -->
    <div class="mapImage">
      <div class="transbox">
        <p>
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text
        </p>
      </div>
      <div class="transbox2">
        <p>
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text sample text sample text
          sample text sample text sample text sample text sample text sample
          text sample text sample text sample text
        </p>
      </div>
      <img alt="Vue" src="./assets/riverBasins.png" contain />
    </div>
  </div>

  <!-- SMALL MULTIPLES -->
  <!-- FILTERS -->
  <!-- <div class="filters">
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
  </div> -->

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
  </div>
  <!--  -->
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- /// -->
  <HelloWorld2 msg="new world" />
  <Modal
    v-on:childToParent="onChildClick"
    v-on:increment="
      if (counter < 10) {
        counter++;
      }
    "
    v-on:decrease="
      if (counter > 0) {
        counter--;
      }
    "
    :scrollPosition="scrollTop"
    :counter="counter"
  >
  </Modal>

  <HelloWorld msg="Welcome to Your Vue.js App" />
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
      filters2: [],
      filters: [
        "2000",
        "2002",
        "2004",
        "2006",
        "2008",
        "2010",
        "2012",
        "2014",
        "2016",
        "2018",
        "2020",
      ],
      counter: 0,
      fromChild: "",
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
          this.filters[this.counter].includes(d.ReportYear) &&
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
    // changeSelectedYear(val) {
    //   this.selectedYear = val;
    // },
    onChildClick(value) {
      this.fromChild = value;
    },
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
  /* margin-top: -100px; */
  margin-left: -10px;
  margin-right: -10px;
  margin-top: -2%;
}
.Intro {
  position: relative;
  left: 0;
  height: 40vh;
  color: white;
  margin-top: 20vh;
  margin-left: 20%;
  margin-right: 20%;

  text-shadow: 3px 3px 0 #000, -1px -1px 0 #000, 1px -1px 0 #000,
    -1px 1px 0 #000;
  font-size: 20px;
}
.viz2 {
  display: grid;
  grid-template-rows: repeat(5, 1fr);
  grid-template-columns: repeat(4, auto);
}
.IntroGlacier {
  position: relative;
  height: 100vh;
}
.mapImage {
  position: inline-block;
  margin-left: -10%;
  height: 100vh;
  /* width: 550px; */
  transform: scale(0.8, 0.8);
}
.mapImage img {
  position: relative;
  /* margin-left: 0%; */
  /* padding-top: 100%; */
  margin-top: 5vh;
  margin-right: 86vw;
  width: 30vw;
  height: auto;
  /* height: 10%;
  width: 10%; */

  transform: scale(1, 1);
}
.title1 {
  font-size: xxx-large;
  margin-bottom: 5vh;
  color: black;
  text-shadow: 3px 3px 0 rgb(73, 192, 192), -1px -1px 0 rgb(73, 192, 192),
    1px -1px 0 rgb(73, 192, 192), -1px 1px 0 rgb(73, 192, 192);
}
.title2 {
  font-size: xx-large;
  margin-bottom: 10vh;
  color: rgb(9, 25, 41);
  text-shadow: 3px 3px 0 rgb(73, 192, 192), -1px -1px 0 rgb(73, 192, 192),
    1px -1px 0 rgb(73, 192, 192), -1px 1px 0 rgb(73, 192, 192);
}
/* .IntroGlacier .bg {
  position: absolute;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: url("./assets/glacier.jpg") center center;
  opacity: 0.9;
  width: 100%;
  height: 100%;
} */
.IntroGlacier .darken {
  position: absolute;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;

  background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.1)),
    url("./assets/glacier.jpg") center center;
  width: 100%;
  height: 100%;
  opacity: 0.9;
}
.margins {
  position: absolute;
  margin-top: 15vh;
}
.map {
  position: relative;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.1)),
    url("./assets/glacier.jpg") center center;
  width: 100%;
  height: 100%;
  opacity: 0.9;
}
.TitleLarge {
  text-align: left;
  margin-left: 25%;
  font-size: 20px;
  margin-bottom: 2%;
  margin-top: 2%;
  /* font-weight: 200; */
}
div.transbox {
  position: absolute;
  margin-top: 5vh;
  margin-left: 40%;
  /* margin-right: 40vw; */

  width: 30vw;
  height: 63vh;
  background-color: #ffffff;
  border: 1px solid black;
  opacity: 0.6;
}
/* background-position: 50% 0; */
div.transbox p {
  margin: 5%;
  font-weight: bold;
  color: #000000;
}
div.transbox2 {
  position: absolute;
  margin-top: 5vh;
  margin-left: 80%;
  /* margin-right: 40vw; */

  width: 30vw;
  height: 63vh;
  background-color: #ffffff;
  border: 1px solid black;
  opacity: 0.6;
}
/* background-position: 50% 0; */
div.transbox2 p {
  margin: 5%;
  font-weight: bold;
  color: #000000;
}
.filters {
  width: 15vw;

  margin-left: 60vw;
}
</style>
