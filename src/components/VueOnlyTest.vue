<template>
  <div class="VueOnlyTest">
    <div class="title-chart-1">
      303(d) list of impaired waterbasins by size {{ checkedUnits }}
    </div>

    <transition-group name="fade">
      <div class="ByBasin" v-for="(key, index) in sortedBasin" :key="key[0]">
        <!--  -->
        <div class="horizontal-title">{{ key[0] }}</div>
        <div class="horizontal-bar" style="height: 50px; overflow: none;">
          <div
            class="horizontal-title2"
            :style="{
              width: xScale(key[1]) + 130 + 'px',
              fill: colors[index],
            }"
          >
            {{ Math.round(key[1] * 10) / 10 }} {{ checkedUnits }}
          </div>
          <svg
            class="wave2"
            viewBox="100 0 500 150"
            preserveAspectRatio="none"
            :style="{
              height: 100 + '%',
              width: xScale(key[1]) + 'px',
              fill: colors[index],
            }"
          >
            <g
              transform="translate(0 -45.5)
                            
                                scale(.5 1)"
            >
              <!-- https://codepen.io/liquidcharcoal/pen/rEeYrw -->
              <path
                d="
                    M0 67
                    C 273,183
                        822,-40
                        1920.00,106 

                    V 359 
                    H 0 
                    V 67
                    Z"
              >
                <animate
                  repeatCount="indefinite"
                  fill="#454599"
                  attributeName="d"
                  dur="10s"
                  values="
                        M0 77 
                        C 473,283
                        822,-40
                        1920,116 

                        V 359 
                        H 0 
                        V 67 
                        Z; 

                        M0 77 
                        C 473,-40
                        1222,283
                        1920,136 

                        V 359 
                        H 0 
                        V 67 
                        Z; 

                        M0 77 
                        C 973,260
                        1722,-53
                        1920,120 

                        V 359 
                        H 0 
                        V 67 
                        Z; 

                        M0 77 
                        C 473,283
                        822,-40
                        1920,116 

                        V 359 
                        H 0 
                        V 67 
                        Z
                        "
                ></animate>
              </path>
            </g>
          </svg>
        </div>
        <!-- <div class="horizontal-bar2" :style="{ height: 50 + 'px' ,width: xScale(key[1]) + 'px'}"></div>  -->

        <!--  -->
        <!-- v-for="key in listOfBasins"
      :key="key" -->

        <div class="section">
          <PercentageDetails
            title="Bar Chart Placeholder"
            xKey="name"
            yKey="amount"
            :data="barChartData"
          />
        </div>

        <div
          class="Details"
          v-for="key2 in FinalByBasin2.get(key[0])"
          :key="key2"
        >
          <div
            class="horizontal-bar4"
            :style="{
              height: (key2[1] / key[1]) * 100 + 'px',
              width: xScale(key[1]) + 'px',
              backgroundColor: 'baby blue',
            }"
          ></div>
          <!-- colors[index] -->
          <div class="Details2" :style="{ display: 'inline' }">
            {{ key2[0] }}
          </div>
          <!-- {{ (key2[1] / key[1]) * 100 }} -->
        </div>

        <!-- {{ Array.from(key[1]) }}  -->

        <!-- {{ key[0] }} -->
        <!-- <div class="wrapper" :style="{ width: xScale(key[1]) + 'px' }">
          <div
            class="horizontal-bar3"
            :style="{ height: 0.1 + 'px', width: xScale(key[1]) + 'px' }"
          ></div>

          <div class="horizontal-text">mercury</div>

          <div
            class="horizontal-bar3"
            :style="{
              fill: '#257afb',
              height: 1 + 'px',
              width: xScale(key[1]) + 'px',
            }"
          ></div>
          <div
            class="horizontal-bar3"
            style="height:2px"
            :style="{ width: xScale(key[1]) + 'px' }"
          ></div>
          <div
            class="horizontal-bar3"
            style="height:3px"
            :style="{ width: xScale(key[1]) + 'px' }"
          ></div>
          <div
            class="horizontal-bar3"
            style="height:10px"
            :style="{ width: xScale(key[1]) + 'px' }"
          ></div>
          <div
            class="horizontal-bar3"
            style="height:10px"
            :style="{ width: xScale(key[1]) + 'px' }"
          ></div>
        </div> -->
        <!-- 
        <ul>
          <li v-for="(basin, label, index) in sortedFinalByBasin2" :key="index">
            <ul>
              <strong>{{ label }}</strong>
              <li v-for="(rule, ruleID) in basin">
                {{ rule[0] }},
                {{ ruleID[0] }}
              </li>
            </ul>
          </li>
        </ul> -->

        <!--  -->

        <div class="horizontal-bar" style="height: 30px; overflow: visible;">
          <svg
            viewBox="0 0 500 150"
            preserveAspectRatio="none"
            :style="{ height: 50 + 'px', width: xScale(key[1]) + 'px' }"
          >
            <path
              d="M0.00,92.27 C216.83,192.92 304.30,8.39 500.00,109.03 L500.00,0.00 L0.00,0.00 Z"
              :style="{ stroke: none, fill: colors[index] }"
            ></path>
            <!-- <path d="M0.00,92.27 C216.83,192.92 304.30,8.39 500.00,109.03 L500.00,0.00 L0.00,0.00 Z" style="stroke: none;fill: #567543;"></path> -->
          </svg>
        </div>

        <!-- </div> -->
      </div>
    </transition-group>
  </div>
</template>

<script>
import * as d3 from "d3";

import PercentageDetails from "./PercentageDetails.vue";

export default {
  components: { PercentageDetails },
  name: "VueOnlyTest",
  data() {
    return {
      colors: [
        "#2828fb",
        "#2898fb",
        "#01d8fd",
        "#267543",
        "#297afb",
        "#2828fb",
        "#01d8fd",
        "#567543",
        "#257afb",
        "#2898fb",
        "#01d8fd",
        "#567543",
        "#297afb",
        "#2898fb",
        "#01d8fd",
        "#567543",
      ],
    };
  },
  // {
  //     “Cahaba”: “#aabbcc”,
  //      “Black Warrior”: “#ddeeff”,

  //      }

  props: {
    Final: Array,
    sortedBasin: Array,
    FinalByBasin: Map,
    checkedUnits: Array,
    listofCauses: Array,
    FinalByBasin2: Map,
  },

  computed: {
    maxPollution() {
      return d3.extent(Array.from(this.FinalByBasin.values()));
    },
    xScale() {
      return d3
        .scaleLinear()
        .domain([0, this.maxPollution[1]])
        .range([0, window.innerWidth / 2]);
    },
    listOfCauses2() {
      return Array.from(new Set(this.filteredFinal.map((d) => d.Causes)));
    },
  },
  methods: {
    // filterByIndex(array, index) {
    //   return array.filter((object) => object.index === index);
    // },
  },
};
</script>

<style>
.horizontal-text {
  position: absolute;
  left: 28%;
  color: darkblue;
}
.horizontal-bar {
  height: 20px;
  background-color: steelblue;
  margin-top: 5px;
  margin-bottom: 5px;
  margin-left: 25%;
  margin-right: 100%;
}
.horizontal-bar2 {
  height: 20px;
  background-color: rgb(150, 143, 42);
  margin-top: 5px;
  margin-bottom: 5px;
  margin-left: 25%;
  margin-right: 100%;
}
.horizontal-bar3 {
  background-color: rgb(150, 111, 134);
  margin-top: 1px;
  margin-bottom: 1px;
  /* margin-left: 25%;
  margin-right: 100%; */
}
.horizontal-bar4 {
  background-color: rgb(150, 111, 134);
  margin-top: 1px;
  margin-bottom: 1px;
  margin-left: 25%;
  margin-right: 100%;
}
/*display: inline-block;*/
.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.Details {
  font-size: 50%;
  text-align: right;
}
.Details2 {
  font-size: 100%;
  text-align: right;
}
.Details:hover > .Details2 {
  font-size: 150%;
  text-align: right;
  opacity: 1;
}
/* .Details:hover {
  cursor: pointer;
  transform: scale(1, 2);
  text-align: center;
} */
/* .wrapper {
  height: 100%;
  width: 50%;
  margin-left: 25%;
  margin-right: 25%;
}
.wrapper:hover {
  cursor: pointer;
  height: 100px;
} */
/* .wrapper:hover > .horizontal-bar3 {
  cursor: pointer; */
/* height: 100px; */
/* transform: scale(1, 2);
  background-color: red;
  margin-top: 15px;
} */
#testpath:hover {
  cursor: pointer;
  /* height: 100px; */
  transform: scale(1, 2);
  background-color: red;
  margin-top: 15px;
}
.ByBasin:hover {
  /* margin-bottom: 100px; */
}
.wave2 {
  position: relative;
  /* position: relative; */
  /* left: 28%; */
  height: 50%;
  width: 100%;
  margin-bottom: 5%;
  /* animation-name: move-left; */
  animation-duration: 4s;
  animation-iteration-count: infinite;
  animation-direction: alternate-reverse;
  z-index: -1;
}

.horizontal-title {
  position: absolute;
  width: 45%;
}
.horizontal-title2 {
  position: absolute;
  display: inline-block;
  /* width: 100%; */
  text-align: right;
  margin-top: 25px;
}
.title-chart-1 {
  font-weight: bold;
  margin-bottom: 50px;
}
@keyframes example {
  0% {
    left: 0px;
    top: 0px;
  }

  50% {
    left: -2000px;
    top: 200px;
  }

  100% {
    left: 0px;
    top: 0px;
  }
}
</style>
