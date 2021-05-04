<template>
  <div class="IntroGlacier">
    <div class="darken"></div>
    <div class="margins"></div>
    <div class="curved-div">
      <span style="color: #fff">20 Years of </span>

      <span style="color: #fff">Water</span>
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
    <div class="curved-div">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#fff"
          fill-opacity="1"
          d="M0,64L60,64C120,64,240,64,360,53.3C480,43,600,21,720,53.3C840,85,960,171,1080,202.7C1200,235,1320,213,1380,202.7L1440,192L1440,0L1380,0C1320,0,1200,0,1080,0C960,0,840,0,720,0C600,0,480,0,360,0C240,0,120,0,60,0L0,0Z"
        ></path>
      </svg>
    </div>
    <h1>A Lush Habitat</h1>
    <div class="drop">
      <svg width="100%" height="101%" viewbox="0 0 20 22">
        <defs>
          <linearGradient id="linear" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
          </linearGradient>
        </defs>
        <path
          fill="white"
          opacity="1"
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
      <p id="bigger1">
        <br />
        Alabama's climate and geographic history makes it one of the most
        ecologically diverse states in the U.S. <br />
      </p>
      <p id="bigger">
        During the Ice Age much of this land remained unfrozen due to its
        lattitude. A combination of proximity to coastal waters and unique
        geological formations around inland waters allowed for evolution to
        continue unabated while most of the planet was covered in ice.
      </p>

      <p id="bigger">
        Today the state ranks number one in the country for aquatic biodiversity
        with more than 450 known species of freshwater fish.<br /><br />
      </p>

      <p></p>
    </div>

    <div class="transbox2">
      <p>
        Black Warrior River <br />
        Photo by Riverkeeper Nelson Brooke
        <a href="https://www.w3schools.com/">Nelson Brooke</a>
      </p>
    </div>
  </div>
  <!--  -->
  <div class="IntroGlacier3" style="height: 90vh">
    <h2>A Troubling History</h2>
    <h3>
      A history of industrial accidents, oversight, and abuse has led to
      disasters that have harmed everything from ponds to rivers and cities.
    </h3>
    <!--  -->
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
    <!--  -->
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
    <!--  -->
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
  <!--  -->
  <div class="map2">
    <h1>The River Basins of Alabama</h1>
    <img alt="Vue" src="./assets/riverBasins.png" />
    <div class="transbox2">
      <p>
        Since 1998 stricter water monitoring policies have been mandated in the
        state in an attempt to control the human and environmental harm caused
        by pollutants.
      </p>
      <p>
        Section 303(d) of the Clean Water Act (CWA) establishes that states are
        to list (the 303(d) list) waters for which technology-based limits alone
        do not ensure attainment of applicable water quality standards.
        <br /><br /><br />
        The Alabama Department of Environmental Management (ADEM) creates these
        lists which can be found here:
        <a href="http://adem.alabama.gov/programs/water/303d.cnt"
          >ADEM 303(d)</a
        >
        <br /><br />
        The past 20 years of impaired 303(d) waters are aggregated and organized
        by the major river basin. Data is used to visualize the scope of water
        contamination by size, cause, and source.This project seeks to analyze
        the progress that has been made during the past 20 years of water
        quality testing.
      </p>
    </div>
    <!--  -->
    <div class="curved-div">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#fff"
          fill-opacity="1"
          d="M0,96L80,80C160,64,320,32,480,48C640,64,800,128,960,133.3C1120,139,1280,85,1360,58.7L1440,32L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"
        ></path>
      </svg>
      <div class="spacer"></div>
    </div>
  </div>
  <!--  -->
  <div class="TitleLarge">
    <h2>
      The Size of the Problem.
    </h2>
  </div>
  <div class="filters">
    <el-checkbox-group v-model="checkedUnits">
      <el-checkbox
        @mousedown="removeOtherUnit"
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
      v-on:hoverMain="onChildClick2"
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
  <!-- SMALL MULTIPLES -->
  <div class="viz2Wrapper">
    <h2>Causes and Sources of Impairment</h2>
    <img id="industry" src="./assets/industry.svg" contain />
    <div class="viz2details">
      <!-- NEW COMPONENT -->
      <div class="filters" id="viz2filters">
        <el-checkbox-group v-model="checkedUnits">
          <el-checkbox
            @mousedown="removeOtherUnit"
            v-for="unit in units"
            :label="unit"
            :key="unit"
            >{{ unit }}</el-checkbox
          >
        </el-checkbox-group>
      </div>
      <StackedSideBar
        :checkedUnits="checkedUnits"
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
        <p style="color: white">
          Man's activities have had a profound, and usually negative, influence
          on freshwater fishes from the smallest streams to the largest
          rivers”-James R. Karr (1981)
        </p>
        <span style="color: #000"> Thdasdasds<br /></span>

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
    <div class="curved-div">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#fff"
          fill-opacity="1"
          d="M0,96L80,80C160,64,320,32,480,48C640,64,800,128,960,133.3C1120,139,1280,85,1360,58.7L1440,32L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"
        ></path>
      </svg>
    </div>
    <h1>What is being done?</h1>
    <img src="./assets/keepers.svg" />

    <div class="transbox">
      <h2>The Riverkeepers</h2>
      <p>
        Various organizations help study and protect the water basins listed in
        this dataset.
        <br /><br />They act independently, but help inform decisions, from
        state agencies such as Alabama Department of Environmental Protection.
        <br />Current news and research regarding each basin linked below or
        visit: http://waterkeepersalabama.org/
        <br />
        <br />
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
      </p>
    </div>
  </div>
  <!-- place modal in section with visualization and look at Alec's codepen  -->
  <!-- position sticky -->
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
  <!-- end HTML skeleton  filler div-->
  <div></div>
</template>

<script>
// BEGIN SCRIPT

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
  //
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
    //////////////////////finalbybasin3
    sortedBasin() {
      let g = Array.from(this.FinalByBasin); //.sort((a,b) => d3.ascending(a.value, b.value))

      var f = g.sort(function(a, b) {
        return b[1] - a[1];
      });
      return f;
    },
    //
    sortedBasinOnlyNames() {
      let g = [];
      for (let i = 0; i < this.sortedBasin.length; i++) {
        g.push(this.sortedBasin[i][0]);
      }
      return g;
    },
    //
    sortedFinalByBasin2() {
      let g = Array.from(this.FinalByBasin2);
      var f = g.sort(function(a, b) {
        return b[1] - a[1];
      });
      return f;
    },
    //
    listOfBasins() {
      return Array.from(new Set(this.Final.map((d) => d.RiverBasin)));
    },
    //
    listOfCauses() {
      return Array.from(new Set(this.Final.map((d) => d.Causes)));
    },
    //
    listOfCausesFiltered() {
      return Array.from(
        new Set(this.filteredFinal.map((d) => d.Causes))
      ).sort();
    },
    //
    filteredSmallMultiples() {
      return this.Final.filter(
        (d) =>
          this.filters[this.counter].includes(d.ReportYear) &&
          this.checkedUnits.includes(d.UnitType)
      );
    },
  },
  //
  components: {
    CauseMultiples,
    VueOnlyTest,
    Modal,
    ModalLegend,
    // Scatter,
    StackedSideBar,
  },
  mounted() {
    //load data
    Promise.all([d3.csv("TESTFinalCompiledCSV2.csv")]).then((data) => {
      this.Final = data[0];
    }),
      window.addEventListener("scroll", this.onScroll);
    // modal positioning
    var x = document.getElementsByClassName("TitleLarge")[0];
    var domRect = x.getBoundingClientRect();
    this.modalYpos = domRect.y;
    var x2 = document.getElementsByClassName("map1")[0];
    var domRect2 = x2.getBoundingClientRect();
    this.modalYposEnd = domRect2.bottom;
  },
  //
  unmounted() {
    window.removeEventListener("scroll", this.onScroll);
  },
  //
  updated() {
    // var x2 = document.getElementsByClassName("map1")[0];
    // var domRect2 = x2.getBoundingClientRect();
    // let g = domRect2.bottom;
    // this.modalYposEnd = g;
  },
  //
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
    removeOtherUnit() {
      if (this.checkedUnits.includes("miles")) {
        this.checkedUnits.splice(0, 1);
        // console.log("hello");
      }
      if (this.checkedUnits.includes("acres")) {
        this.checkedUnits.splice(0, 1);
        // console.log("goodbye");
      }
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
  background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0)),
    url("./assets/CoosaDam.jpg") center center;
  width: 100%;
  height: 100vh;
  margin-bottom: 5%;
  margin-top: -5%;
}
.new .curved-div {
  margin-top: 16%;
}
.new .curved-div p {
  margin-top: 0%;
  margin-left: 10%;
  margin-right: 10%;
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
  z-index: 0;
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
  color: #000;
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
  margin-top: 6%;
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
  z-index: 1;
  margin-top: 15%;
  margin-right: 10%;
  margin-left: 15%;
}

.map h1 {
  margin-right: 0%;
  margin-top: 1%;
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: span 2;
  font-size: 3em;
  z-index: 1;
  color: #000;
  margin-left: 45%;
  margin-top: 3%;
}
.map {
  display: grid;
  position: relative;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(
      to right,
      rgba(255, 255, 255, 0),
      rgba(59, 45, 4, 0.198)
    ),
    linear-gradient(to left, rgba(255, 255, 255, 0), rgba(23, 99, 143, 0.616)),
    url("./assets/cahaba.jpg");
  background-repeat: no-repeat;
  width: 100%;
  height: 100vh;
  opacity: 1;
  margin-top: 7%;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px 100px 100px auto;
  margin-bottom: -1%;
  background-size: 100% 100%;
}
.map .transbox p {
  margin-top: 5%;
  font-size: 1.1em;
  margin-left: 5%;
  margin-right: 5%;
}
.map .curved-div {
  margin-top: -3%;

  position: relative;
  grid-column-start: 1;
  grid-column-end: 6;
  grid-row-start: 1;
  grid-row-end: 1;
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
.map .transbox h2 {
  margin-top: 2%;
  margin-bottom: -2%;
  margin-left: 5%;
  margin-right: 5%;
}
.map .transbox {
  margin-left: 55%;
  margin-right: 5%;
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
  margin-top: -12.5%;
  margin-left: -72%;
  border-radius: 50px;
}

.map1 p {
  grid-column-start: 3;
  grid-column-end: 3;
  margin-right: 0%;
  grid-row-start: 3;
  grid-row-end: span 2;
  font-size: 1.8em;
  font-weight: bold;
  background-color: none;
  text-align: center;
  z-index: 1;
}
.map img {
  transform: scale(9, 9);
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 2;
  border-radius: 20px;
  margin-top: -5%;
  height: 100%;
  margin-left: 35%;
  margin-top: 13%;
}
.map .transbox {
  grid-column-start: 1;
  grid-column-end: 4;
  grid-row-start: 2;
  grid-row-end: 3;
  border-radius: 50px;
  background-color: #ffffff;
  border: none;
  opacity: 0.9;
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
  margin-top: -15px;
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
  transform: scale(0.9, 0.9);
}
.IntroGlacier3 > h2 {
  margin-left: 44%;
  margin-right: 10%;
  font-size: 3em;
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 2;
  color: black;
}
.IntroGlacier3 > h3 {
  text-align: left;
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
.map1 {
  display: grid;
  position: relative;
  z-index: -1;
  position: sticky;
  margin-top: 15%;
  margin-bottom: 25%;
  /* background: url("./assets/CoosaDam.jpg") center no-repeat; */
  width: 100%;
  background-size: 100% 80%;
  height: 50vh;
  opacity: 1;
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
  margin-top: 10%;
  background-image: linear-gradient(
      to left,
      rgb(116, 156, 243, 0.4),
      rgb(158, 188, 216, 0.7)
    ),
    linear-gradient(rgb(158, 188, 216, 0.1), rgba(0, 104, 40, 1));
  background-repeat: no-repeat;
  background-size: 100% 100%;
  width: 100%;
  height: 100vh;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px 100px 100px auto;
}
.map3 {
  margin-top: -1%;
  display: grid;
  position: relative;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0%;
  right: 0%;
  background-image: linear-gradient(
      rgba(69, 143, 161, 0.075),
      rgba(0, 0, 0, 0.4)
    ),
    url("./assets/Blackwarrior.jpg");
  background-repeat: no-repeat;
  background-size: 100% 100%;
  width: 100%;

  margin-bottom: 2%;
  height: 100vh;
  opacity: 1;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 10% auto 100px auto;
}
.map2 img {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 2;
  grid-row-end: span 2;
  margin-left: -2%;
  border-radius: 20px;
}

.map2 h1 {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: span 2;
  z-index: 1;
  font-size: 3em;
  margin-left: 35%;
  margin-top: 17%;
}
.TitleLarge {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 2em;
  background-image: linear-gradient(rgba(23, 99, 143, 0.267), white 85%);
  height: 25vh;
}
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
div.transbox3 p {
  font-weight: bold;
  font-size: 18px;
  color: rgb(0, 0, 0);
}

div.transbox3 {
  position: absolute;
  margin-left: 12%;
  margin-top: 4%;
  text-align: left;
  margin-right: 68%;
  grid-column-start: 3;
  grid-column-end: 3;
  grid-row-start: 2;
  grid-row-end: 4;
  border-radius: 55px;
}
.map .transbox2 {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 5;
  grid-row-end: 6;
  border-radius: 55px;
  opacity: 0.9;
  background-color: #ffffff;
  opacity: 1;
  margin-bottom: 10%;
  margin-top: 17%;
  margin-left: 53%;
  margin-right: 5%;
}
.map .transbox2 p {
  margin-top: 2%;
  font-size: 1em;
}
.map2 .transbox2 {
  margin-left: 37%;
  grid-column-start: 3;
  grid-column-end: 3;
  grid-row-start: 3;
  grid-row-end: 5;
  border-radius: 55px;
  opacity: 1;
}

.map3 #bigger {
  margin-left: -25%;
  margin-right: -45%;
  margin-bottom: 5%;
  margin-top: 5%;
}
.map3 #bigger1 {
  margin-left: -5%;
  margin-right: -20%;
  margin-bottom: 10%;
  margin-top: 5%;
  font-size: 1.5em;
}
.map3 .transbox2 {
  margin-left: 85%;
  margin-right: 0%;
  margin-top: 25%;
  margin-bottom: 0%;
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 5;
  grid-row-end: 5;
  opacity: 1;
}
.map3 .transbox3 {
  margin-top: 15%;
  margin-left: 11%;
  margin-right: 74%;
}
.map3 .transbox2 p {
  font-weight: bold;
  font-size: 12px;
  color: #ffffff;
  margin: 20px;
  opacity: 0.7;
}
.map3 .drop {
  margin-top: 10%;
}
div.transbox2 p {
  font-weight: bold;
  font-size: 120px;
  color: #000000;
  margin: 20px;
}

#industry {
  position: sticky;
  margin-top: -5%;
  margin-right: 78%;
  margin-bottom: -0.8%;
  width: 19.99vw;
  z-index: -1;
}
#agriculture {
  position: absolute;
  margin-top: 203%;
  margin-left: -205px;
  width: 20vw;
  height: 10%;
}
.viz2Wrapper {
  display: inline-block;
  margin-right: 0%;
  margin-top: 5%;
  margin-bottom: 7%;
  margin-left: 0%;
}
.viz2Wrapper h2 {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 3em;
  margin-bottom: 1%;
  margin-left: 3%;
}

.viz2Wrapper2 {
  display: inline-block;
  margin-right: 0%;
  margin-top: -1%;
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
  margin-top: 7%;
}
.map2 .transbox2 p {
  margin-bottom: 4%;
  text-align: left;
  font-size: 1.3em;
  opacity: 1;
}
.map2 .curved-div {
  grid-column-start: 1;
  grid-column-end: 6;
  grid-row-start: 1;
  grid-row-end: 1;
  margin-top: -6.1%;
}
.map3 .curved-div {
  grid-column-start: 1;
  grid-column-end: 6;
  grid-row-start: 1;
  grid-row-end: 1;
  margin-top: -8%;
  transform: scale(1, 0.6);
}
.map2 > .curved-div > span {
  display: inline-block;
  margin-right: 45%;
}
.map2 > .curved-div > p {
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
  font-size: 3.5em;
  margin-top: 1%;
  margin-left: -10%;
  margin-right: 0%;
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

#app > div.map3 > h1 {
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 2;
  font-size: 3em;
  margin-left: 75%;
  z-index: 1;
  color: #000;
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
  margin-left: 65%;
  margin-top: 35%;
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
  margin-top: 0%;
}
.droptop {
  margin-left: 50%;
  margin-top: -45%;
  transform: scale(1.1, 0.5);
  grid-column-start: 3;
  grid-column-end: 5;
  grid-row-start: 1;
  grid-row-end: 6;
}
.filters {
  position: relative;
  text-align: center;
  margin-right: 55px;
  margin-bottom: -32px;
  margin-left: 550px;
}
#viz2filters {
  position: relative;
  text-align: center;
  margin-right: 0;
  margin-bottom: 0px;
  margin-left: 0;
}
</style>
