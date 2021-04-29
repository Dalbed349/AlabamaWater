<template>
  <div class="IntroGlacier">
    <div class="darken"></div>
    <div class="margins"></div>
    <div class="curved-div">
      <span style="color: #fff">20 Years of </span>

      <span style="color: #98F5FF">Water</span>
      <p style="color: #fff">Visualising Alabama's List of Impaired Waters</p>
      <svg viewBox="0 0 1440 319">
        <path
          fill="#fff"
          fill-opacity="1"
          d="M0,32L48,80C96,128,192,224,288,224C384,224,480,128,576,90.7C672,53,768,75,864,96C960,117,1056,139,1152,149.3C1248,160,1344,160,1392,160L1440,160L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
        ></path>
      </svg>
      <div class="spacer"></div>
    </div>
  </div>
  <!--  -->
  <div class="IntroGlacier2"></div>
  <!--  -->
  <div class="map3">
    <div class="curved-div"></div>
    <h1>A Sprawling Wildlife</h1>
    <div class="drop">
      <svg width="100%" height="100%" viewbox="0 0 20 22">
        <defs>
          <linearGradient id="linear" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
          </linearGradient>
        </defs>
        <path
          fill="white"
          opacity=".7"
          stroke="url(#linear)"
          stroke-width=".2"
          transform="scale(23 25)"
          d="M15 3
           Q16.5 6.8 25 18
           A12.8 12.8 0 1 1 5 18
           Q13.5 6.8 15 3z"
        />
      </svg>
    </div>

    <div class="transbox3">
      <p>
        <br />
        Alabama’s climate and geographic history makes it one of the most
        ecologically diverse states in the U.S. <br /><br />
        During the Ice Age much of this land remained unfrozen due to its
        lattitude. A combination of proximity to coastal waters and unique
        geological formations around inland waters allowed for evolution to
        continue unabated while most of the planet was covered in ice.
        <br /><br />
        Today the state ranks number one in the country for aquatic biodiversity
        with more than 450 known species of fish.<br /><br />
      </p>
    </div>
    <div class="transbox2">
      <p>
        Black Warrior River <br />
        Photo by Riverkeeper
        <a href="https://www.w3schools.com/">Nelson Brooke</a>
      </p>
    </div>
  </div>
  <!--  -->

  <div class="IntroGlacier3" style="height: 90vh">
    <h2>A Troubling History</h2>
    <h3>
      At the same time, a history of industrial accidents and abuse has led to
      disasters that have harmed everything from ponds to coastlines and cities.
    </h3>

    <div class="drop">
      <p class="droptxt">Monsanto PCB plant in Anniston</p>
      <svg
        width="100%"
        height="100%"
        viewbox="0 0 20 22"
        @mouseenter="dropHover = true"
        @mouseleave="dropHover = null"
      >
        <defs>
          <linearGradient id="linear" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
            <pattern
              id="img1"
              patternUnits="userSpaceOnUse"
              width="42"
              height="16"
            >
              <image
                href="./assets/monsantoAnniston.jpg"
                x="-6"
                y="0"
                width="42"
                height="16"
              />
            </pattern>
          </linearGradient>
        </defs>
        <path
          fill="url(#img1)"
          opacity="1"
          stroke="url(#linear)"
          stroke-width=".2"
          transform="scale(23 25)"
          d="M15
        3 Q16.5 6.8 25 18 A12.8 12.8 0 1 1 5 18 Q13.5 6.8 15 3z"
        />
      </svg>
    </div>
    <div class="drop2">
      <p class="droptxt">Coal Ash Waste at Barry Power Plant</p>
      <svg width="100%" height="100%" viewbox="0 0 20 22">
        <defs>
          <linearGradient id="linear" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
          </linearGradient>

          <pattern
            id="img2"
            patternUnits="userSpaceOnUse"
            width="100"
            height="55"
          >
            <image
              href="./assets/BarryAsh.jpg"
              x="-45"
              y="0"
              width="100"
              height="55"
            />
          </pattern>
        </defs>
        <path
          fill="url(#img2)"
          opacity="1"
          stroke="url(#linear)"
          stroke-width=".2"
          transform="scale(12 12)"
          d="M15 3
           Q16.5 6.8 25 18
           A12.8 12.8 0 1 1 5 18
           Q13.5 6.8 15 3z"
        />
      </svg>
    </div>
    <div class="drop3">
      <p class="droptxt">Lay Dam Coosa River</p>
      <svg width="100%" height="100%" viewbox="0 0 20 22">
        <defs>
          <linearGradient id="linear" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
          </linearGradient>
          <pattern
            id="img3"
            patternUnits="userSpaceOnUse"
            width="45"
            height="65"
          >
            <image
              href="./assets/LayDamCoosa.jpg"
              x="-4"
              y="-11"
              width="45"
              height="65"
            />
          </pattern>
        </defs>
        <path
          fill="url(#img3)"
          opacity="1"
          stroke="url(#linear)"
          stroke-width=".2"
          transform="scale(14 13)"
          d="M15 3
           Q16.5 6.8 25 18
           A12.8 12.8 0 1 1 5 18
           Q13.5 6.8 15 3z"
        />
      </svg>
    </div>
  </div>

  <div class="map2">
    <img alt="Vue" src="./assets/riverBasins.png" />
    <div class="transbox2">
      <p>
        Since 1998 stricter water monitoring policies have been mandated in the
        state in an attempt to control the human and environmental harm caused
        by pollutants. This project seeks to analyze the progress that has been
        made during the past 20 years of water quality testing.<br /><br />
        Section 303(d) of the Clean Water Act (CWA) establishes that states are
        to list (the 303(d) list) waters for which technology-based limits alone
        do not ensure attainment of applicable water quality standards.
        <br /><br />
        The Alabama Department of Environmental Management (ADEM) creates these
        lists which can be found at:
        <a href="http://adem.alabama.gov/programs/water/303d.cnt"
          >http://adem.alabama.gov/programs/water/303d.cnt</a
        >
        <br /><br />
        The past 20 years of impaired (303d) waters are aggregated and organized
        by the major river basin. Data is used to visualize the scope of water
        contamination by size, cause, and source.
      </p>
    </div>

    <div class="curved-div">
      <p style="color: transparent">
        Visualising Alabama's List of Impaired Waters
      </p>
      <span style="color: #000"> The River Basins of Alabama <br /></span>
      <!-- <span style="color: #fff">20 Years of </span> -->

      <svg viewBox="0 0 1440 319">
        <path
          fill="#fff"
          fill-opacity="1"
          d="M0,32L48,80C96,128,192,224,288,224C384,224,480,128,576,90.7C672,53,768,75,864,96C960,117,1056,139,1152,149.3C1248,160,1344,160,1392,160L1440,160L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
        ></path>
      </svg>
      <div class="spacer"></div>
    </div>
  </div>

  <!--  -->
  <div class="TitleLarge">
    <h2>The length of the problem...</h2>
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
      :fromChild="fromChild"
      v-on:hoverMain="onChildClick2"
    />
  </div>

  <!--  -->

  <div class="map1">
    <h1>Where could this all come from?</h1>
    <!-- <div class="transbox">
      <p>
        Where could this all come from?
      </p>
    </div> -->
    <div class="transbox2">
      <p>
        Man’s activities have had a profound, and usually negative, influence on
        freshwater fishes from the smallest streams to the largest rivers”-James
        R. Karr (1981)
        <br /><br />
        Researcherers from various discplines have tackled this issued. 1. 2. 3.
      </p>
    </div>
    <!-- <img alt="Vue" src="./assets/logo.png" contain /> -->
  </div>

  <!-- SMALL MULTIPLES -->
  <!-- FILTERS -->

  <!-- -->
  <div class="viz2Wrapper">
    <h2>The offending contaminants and their sources</h2>
    <img id="industry" src="./assets/industry.svg" contain />
    <div class="viz2details">
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
      <!-- <img id="agriculture" src="./assets/cowfield.png" contain /> -->
      <!-- NEW COMPONENT -->
      <StackedSideBar
        :data="filteredSmallMultiples"
        :basin="hoverSecondVis"
        :cause="hoverSecondVisCause"
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
        :counter="counter"
      ></StackedSideBar>
    </div>
    <div class="viz2Wrapper2">
      <div class="viz2">
        <CauseMultiples
          v-for="key in sortedBasin"
          :key="key"
          :data="filteredSmallMultiples"
          :basin="key[0]"
          v-on:hoverSecondVis="onChildClick3"
          v-on:hoverSecondVisCause="onChildClick4"
        >
        </CauseMultiples>
      </div>
    </div>
  </div>
  <!-- <div class="new">
    <div class="backgroundDam">
      <div class="curved-div">
        <p style="color: transparent">
          Visualising Alabama's List of Impaired Waters
        </p>
        <span style="color: #000"> The River Basins of Alabama <br /></span>

        <svg viewBox="0 0 1440 319">
          <path
            fill="#fff"
            fill-opacity="1"
            d="M0,32L48,80C96,128,192,224,288,224C384,224,480,128,576,90.7C672,53,768,75,864,96C960,117,1056,139,1152,149.3C1248,160,1344,160,1392,160L1440,160L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
          ></path>
        </svg>
        <div class="spacer"></div>
      </div>
    </div>
  </div> -->
  <!-- <Scatter> </Scatter> -->
  <div class="map">
    <h1>More Information</h1>
    <div class="transbox">
      <h2>The Riverkeepers</h2>
      <p>
        Various organizations help study and protect the water basins listed in
        this dataset.
        <br /><br />They act independently, but help inform decisions, from
        state agencies such as Alabama Department of Environmental Protection.
        <br /><br />Current news and research regarding each basin linked below
        or visit: http://waterkeepersalabama.org/
        <br />
        <br />

        <img src="./assets/waterkeepermap.jpg" />
      </p>
      <p id="resourcelinks">
        https://www.mobilebaykeeper.org/<br />
        https://blackwarriorriver.org/<br />
        https://www.tennesseeriverkeeper.org/<br />
        https://littleriverwaterkeeper.org/<br />
        https://coosa.org/<br />
        https://chattahoochee.org/<br />
        https://cahabariverkeeper.org/<br />
        https://www.choctawhatcheeriver.org/<br />
        http://www.hurricanecreek.org/<br />
      </p>
    </div>
    <div class="transbox2">
      <p>
        This project was prepared as part of the Parson's Data Visualization
        (M.S.) Program. <br /><br />
        Files and documentation can be found at
        <a href="https://github.com/Dalbed349/AlabamaWater/"
          >github.com/Dalbed349/AlabamaWater/</a
        >
        <br /><br />For more water quality information visit:<a
          href="http://adem.alabama.gov/programs/water/waterquality.cnt"
        >
          ADEM water quality monitoring</a
        >
      </p>
    </div>
  </div>
  <Modal
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
    :modalYpos="modalYpos"
    :modalYposEnd="modalYposEnd"
    :hoverCentral="hoverCentral"
    :sortedBasin="sortedBasin"
    :sortedBasinOnlyNames="sortedBasinOnlyNames"
  >
  </Modal>
  <ModalLegend
    v-on:childToParent="onChildClick"
    :scrollPosition="scrollTop"
    :counter="counter"
    :modalYpos="modalYpos"
    :modalYposEnd="modalYposEnd"
    :listofCauses="listOfCauses"
    :listOfCausesFiltered="listOfCausesFiltered"
  >
  </ModalLegend>
  <div></div>
</template>

<script>
import VueOnlyTest from "./components/VueOnlyTest.vue";
import CauseMultiples from "./components/CauseMultiples.vue";
// import Scatter from "./components/Scatter.vue";
import Modal from "./components/Modal.vue";
import * as d3 from "d3";
import ModalLegend from "./components/ModalLegend.vue";
import StackedSideBar from "./components/StackedSideBar.vue";

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
  data() {
    return {
      hovertrue: null,
      scrollTop: 0,
      Final: [],
      MacroFinal: [],
      filters2: [],
      modalYpos: 0,
      dropHover: null,
      hoverSecondVisCause: null,
      modalYposEnd: 0,
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
      hoverCentral: "",
      hoverSecondVis: null,
      hoverValue: "",
      fromChild: "",
      checkAll: false,
      checkedUnits: ["miles"],
      units: unitOptions,
      isIndeterminate: true,
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
    ////
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
    ///
    FinalByBasin2() {
      if (!this.filteredFinal) {
        return new Map();
      }
      let g = d3.rollup(
        this.filteredFinal,
        (values) => d3.sum(values.map((d) => +d["Size"])),
        (d) => d["RiverBasin"],
        (d) => d["Causes"]
      );
      return g;
    },
    ///
    FinalByBasin3() {
      if (!this.filteredFinal) {
        return new Map();
      }
      let g = d3.rollup(
        this.filteredFinal,
        (values) => uniqueSum(values),
        (d) => d["RiverBasin"]
      );

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
    sortedBasinOnlyNames() {
      let g = [];
      for (let i = 0; i < this.sortedBasin.length; i++) {
        g.push(this.sortedBasin[i][0]);
      }
      return g;
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
      return Array.from(new Set(this.Final.map((d) => d.Causes)));
    },
    listOfCausesFiltered() {
      return Array.from(new Set(this.filteredFinal.map((d) => d.Causes)));
    },
    filteredSmallMultiples() {
      // if (!this.Final) {
      //   return null;
      // }

      return this.Final.filter(
        (d) =>
          this.filters[this.counter].includes(d.ReportYear) &&
          d.UnitType == "miles"
      );
    },
  },

  components: {
    CauseMultiples,
    VueOnlyTest,
    Modal,
    ModalLegend,
    // Scatter,
    StackedSideBar,
  },
  mounted() {
    Promise.all([d3.csv("TESTFinalCompiledCSV.csv")]).then((data) => {
      this.Final = data[0];
      // console.log(this.Final);
    }),
      window.addEventListener("scroll", this.onScroll);

    var x = document.getElementsByClassName("TitleLarge")[0];
    var domRect = x.getBoundingClientRect();
    this.modalYpos = domRect.y;
    var x2 = document.getElementsByClassName("map1")[0];
    var domRect2 = x2.getBoundingClientRect();
    this.modalYposEnd = domRect2.bottom;
  },

  unmounted() {
    window.removeEventListener("scroll", this.onScroll);
  },
  // updated() {
  //   var x2 = document.getElementsByClassName("map1")[0];
  //   var domRect2 = x2.getBoundingClientRect();
  //   let g = domRect2.bottom;

  //   this.modalYposEnd = g;
  // },
  methods: {
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
    onScroll(/*event*/) {
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
.new {
  position: relative;
  display: inline-block;
  margin: auto;
  background-repeat: no-repeat;
  background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.1)),
    url("./assets/CoosaDam.jpg") center center;
  width: 100%;
  height: 100vh;
}
.new .curved-div {
  margin-top: 16%;
}

.section2 {
  display: block;
}
.section {
  display: block;
}
.viz2details {
  position: absolute;
  margin-left: 1%;

  width: 20vw;
  height: 90%;
  border-radius: 15px;
  background-color: #5696bc;
  opacity: 1;
}
#app {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: -100px; */
  margin-left: -10px;
  margin-right: -10px;
  margin-top: -2%;
  display: flex;
  flex-direction: column;
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
  grid-template-rows: repeat(5);
  grid-template-columns: repeat(4, auto);
}
.IntroGlacier {
  position: relative;
  height: 100vh;
}
.IntroGlacier2 {
  display: grid;

  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25%;
  margin-top: 15%;
}
.IntroGlacier3 {
  display: grid;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px 100px 100px auto;
  margin-top: 15%;
}

#app > div.TitleLarge > h2 {
  margin-top: 8%;
  margin-left: 25vw;
  text-align: left;
}

.map2 .curved-div svg {
  width: 100%;
  height: auto;
  text-align: top;
  margin-top: -1%;
}

.IntroGlacier .darken {
  position: absolute;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(rgba(0, 0, 0, 0), rgba(0, 0, 0, 1)),
    url("./assets/glacier.jpg") center center;
  width: 100%;
  height: 100%;
  opacity: 0.9;
  background-size: 100vw;
}
.margins {
  margin-top: 35vh;
}

.map1 img {
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 2;
  grid-row-end: span 2;
}
.map1 h1 {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: span 2;
  font-size: 3em;
  color: #98f5ff;
  /* color: #ffffff; */
}
.map h1 {
  margin-right: 0%;
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: span 2;
  font-size: 3em;
  /* color: #98f5ff; */
  /* color: #fff; */
  /* color: #000; */
  color: #2c3e50;
}
.map .transbox p {
  margin-top: 5%;
  font-size: 1.1em;
  margin-left: 5%;
  margin-right: 5%;
}
.map .transbox h2 {
  margin-top: 2%;
  margin-bottom: -2%;
  margin-left: 5%;
  margin-right: 5%;
}
.map .transbox {
  margin-left: 60%;
  margin-right: 0%;
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: span 2;
  font-size: 1em;
  color: #000000;
  margin-bottom: -20.5%;
  margin-top: 1%;
}
.map .transbox img {
  position: absolute;
  height: 45%;
  margin-top: -13%;
  margin-left: -72%;
  border-radius: 50px;
}

.map1 .transbox {
  grid-column-start: 2;

  grid-row-start: 2;
  grid-row-end: span 2;

  background-color: none;
  border: 1px solid rgb(255, 255, 255);
}
.map .transbox {
  grid-column-start: 1;
  grid-column-end: 4;
  grid-row-start: 2;
  grid-row-end: 3;
  border-radius: 50px;
  background-color: #ffffff;
  border: none;
  opacity: 0.8;
  font-weight: bold;

  color: #000000;
}
.map1 .transbox2 {
  grid-column-end: 4;
  grid-row-start: 4;
  grid-row-end: span 2;
  margin-left: 25%;
  margin-right: 25%;
  background-color: #ffffff;
  opacity: 0.6;
  margin-bottom: 15%;
  margin-top: -5%;
  border-radius: 50px;
}
.drop {
  /* margin-left: 45vw; */
  margin-top: -80px;
  margin-left: 0%;
  grid-column-start: 3;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 6;
}
.IntroGlacier3 .drop {
  margin-left: 25%;
  margin-right: 25%;
  margin-bottom: -5%;
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 6;
  /* background: url("./assets/monsantoAnniston.jpg") center no-repeat; */
}
.IntroGlacier3 > h2 {
  margin-left: 50%;
  margin-right: 25%;
  font-size: 3em;
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 2;
  /* background: url("./assets/monsantoAnniston.jpg") center no-repeat; */
}
.IntroGlacier3 > h3 {
  grid-column-start: 3;
  grid-column-end: 5;
  grid-row-start: 2;
  grid-row-end: 5;
  margin-left: 55%;
  margin-right: 10%;
  margin-top: -2%;
}
.IntroGlacier3 .drop2 {
  margin-left: 74%;
  margin-right: 0%;
  margin-bottom: 5%;

  margin-top: 18%;
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 6;
  /* background: url("./assets/monsantoAnniston.jpg") center no-repeat; */
}
.IntroGlacier3 .drop3 {
  grid-column-start: 2;
  grid-column-end: span3;
  grid-row-start: 1;
  grid-row-end: 6;

  /* background: url("./assets/monsantoAnniston.jpg") center no-repeat; */
}
/* linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0)), */
.map {
  display: grid;
  position: relative;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: url("./assets/Locust-Fork-River.jpg") center center;
  width: 99%;
  height: 100vh;
  opacity: 0.9;
  margin-top: 1%;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px 100px 100px auto;
  margin-left: 0.5%;
  margin-bottom: -1%;
  border-radius: 350px;
}

.map1 {
  display: grid;
  position: relative;
  z-index: -1;
  top: 0;
  bottom: 0;
  margin-top: 200px;
  margin-left: 0.5%;
  margin-bottom: 100px;
  left: 0;
  right: 0;
  background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.1)),
    url("./assets/acesimg.jpg") center center;
  width: 99%;
  border-radius: 350px;
  background-size: 100% 100%;
  height: 100vh;
  opacity: 0.9;
  background-repeat: no-repeat;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px 100px 100px auto;
}
.map2 {
  display: grid;
  position: relative;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  /* background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.1)),
    url("./assets/glacier.jpg") center center; */
  background-image: linear-gradient(
      to right,
      rgba(255, 255, 255, 0),
      rgba(59, 45, 4, 0.198)
    ),
    linear-gradient(to left, rgba(255, 255, 255, 0), rgba(23, 99, 143, 0.616)),
    url("./assets/cahaba.jpg");
  background-repeat: no-repeat;
  background-size: 100% 100%;
  width: 100%;
  height: 100vh;
  opacity: 0.9;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px 100px 100px auto;
}
.map3 {
  display: grid;
  position: relative;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 2%;
  right: 2%;
  /* background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.1)),
    url("./assets/glacier.jpg") center center; */
  background-image: linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.8)),
    url("./assets/Blackwarrior.jpg");
  border-radius: 350px;
  background-repeat: no-repeat;
  background-size: 100% 100%;
  width: 96%;
  height: 100vh;
  opacity: 0.9;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 10% auto 100px auto;
}
.map2 img {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 2;
  grid-row-end: span 2;
  margin-left: 5%;
  border-radius: 30px;
  border: 5px solid rgb(155, 197, 187);
}
.TitleLarge {
  /* text-align: left;
  margin-left: 25%; */
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 30px;
  background-image: linear-gradient(rgba(23, 99, 143, 0.267), white 85%),
    linear-gradient(to right, rgba(59, 45, 4, 0.198), white);
  /* margin-bottom: 1%;
  margin-top: 4%; */
  height: 25vh;
}
/* rgb(46, 115, 155) */
div.transtitle {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 2;
  background-color: #ffffff;
  border: 1px solid black;

  opacity: 0.5;
}
div.transbox {
  margin-left: 25%;
  margin-right: 25%;
  grid-column-start: 2;
  grid-column-end: 5;
  grid-row-start: 1;
  grid-row-end: 1;
  background-color: #ffffff;
  border: 1px solid black;
  opacity: 1;
}
/* background-position: 50% 0; */
div.transbox3 p {
  font-weight: bold;
  font-size: 21px;
  color: rgb(19, 70, 77);
}

div.transbox3 {
  position: absolute;
  margin-left: 8%;

  margin-top: 1%;

  text-align: center;
  margin-right: 69%;
  grid-column-start: 3;
  grid-column-end: 3;
  grid-row-start: 2;
  grid-row-end: 4;

  /* background-color: #ffffff;

  opacity: 0.8; */
  border-radius: 55px;
}
.map .transbox2 {
  /* margin-left: 50%; */
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 5;
  grid-row-end: 6;
  border-radius: 55px;
  opacity: 0.9;
  background-color: #ffffff;
  /* border: 1px solid black; */
  opacity: 0.8;
  margin-bottom: 10%;
  margin-top: 17%;
  margin-left: 25%;
  margin-right: 25%;
}
.map .transbox2 p {
  margin-top: 2%;
  font-size: 1em;
}
.map2 .transbox2 {
  margin-left: 50%;
  grid-column-start: 3;
  grid-column-end: 3;
  grid-row-start: 5;
  grid-row-end: 5;
  border-radius: 55px;
  opacity: 0.7;
  background-color: #ffffff;

  /* border: 1px solid black; */
}
.map3 .transbox2 {
  margin-left: 50%;
  grid-column-start: 3;
  grid-column-end: 3;
  grid-row-start: 5;
  grid-row-end: 5;
  border-radius: 55px;
  opacity: 0.9;
  background-color: #ffffff;
  /* border: 1px solid black; */
  opacity: 0.6;
}
div.transbox2 p {
  font-weight: bold;
  font-size: 12px;
  color: #000000;
  margin: 20px;
}
.viz2Wrapper {
  display: inline-block;
  margin-right: 0%;
  margin-top: 2%;
  margin-bottom: 7%;
  margin-left: 0%;
  /* background-image: url("./assets/industry.svg");
  background-repeat: no-repeat;
  background-size: 100% 100%; */
}
#industry {
  position: absolute;
  margin-top: -5%;
  margin-left: -94px;
  width: 20vw;
}
#agriculture {
  position: absolute;
  margin-top: 203%;
  margin-left: -205px;
  width: 20vw;
  height: 10%;
}
.viz2Wrapper h2 {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 3em;
  margin-bottom: 0%;
  margin-left: 5%;
}

.viz2Wrapper2 {
  display: inline-block;
  margin-right: 0%;
  margin-top: 2%;
  margin-bottom: 2%;
  margin-left: 20%;
}

.wrapper {
  display: inline-block;
  margin-right: 2%;
  margin-top: 5%;
  margin-left: 2%;
}
@media (min-width: 1440x) {
}

.map2 .transbox2 {
  margin-bottom: 7%;
  margin-top: -1%;
  text-align: left;
}
.map2 .transbox2 p {
  margin-bottom: 4%;
  text-align: left;
  font-size: 20px;
  opacity: 1;
}
.map2 .curved-div {
  grid-column-start: 1;
  grid-column-end: 6;
  grid-row-start: 1;
  grid-row-end: 1;
  transform: rotate(180deg);
}
/* .map2 .curved-div span {
  grid-column-start: 1;
  grid-column-end: 6;
  grid-row-start: 1;
  grid-row-end: 1;
  transform: rotate(180deg);
} */
.map2 > .curved-div > span {
  -webkit-transform: rotate(180deg);
  display: inline-block;
  margin-right: 45%;
  /* margin-top: 10%; */
}
.map2 > .curved-div > p {
  -webkit-transform: rotate(180deg);
}

.curved-div {
  position: block;
  height: 55vh;
  width: 100%;
}
.curved-div span {
  font-size: 8rem;
  font-weight: bold;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: black;
}
.map2 .curved-div span {
  font-size: 3.5rem;
  margin-top: 1%;
  font-weight: bold;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  -webkit-text-stroke-width: 0px;
  -webkit-text-stroke-color: rgb(0, 0, 0);
}
.curved-div p {
  font-size: 2rem;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
.curved-div svg {
  width: 100%;
  height: auto;
  text-align: top;
  margin-top: 2%;
}
.map3 .transbox2 {
  margin-left: 65%;
  margin-right: 15%;
  margin-top: 25%;
  margin-bottom: 3%;
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 5;
  grid-row-end: 5;
  opacity: 0.5;
}
#app > div.map3 > h1 {
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 2;
  font-size: 3em;

  color: #98f5ff;
}
.drop .droptxt:hover {
  opacity: 1;
  color: red;
}
.drop2 .droptxt:hover {
  opacity: 1;
  color: red;
}
.drop3 .droptxt:hover {
  opacity: 1;
  color: red;
}
.drop .droptxt {
  position: absolute;
  margin-left: 33%;
  margin-top: 25%;
  opacity: 0.1;
  height: 50px;
}

.drop2 .droptxt {
  position: absolute;
  margin-left: -9%;
  margin-top: 23%;
  opacity: 0.1;
}

.drop3 .droptxt {
  position: absolute;
  margin-left: 13%;
  margin-top: 3%;
  opacity: 0.11;
}

.spacer {
  display: block;
  height: 2vh;
  width: 100%;
}
.transbox3 svg {
  position: absolute;
}
#resourcelinks {
  font-size: 0.9em;
  margin-top: -2%;
}
</style>
