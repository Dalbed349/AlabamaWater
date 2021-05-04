<template>
  <div class="VueOnlyTest">
    <div class="darken"></div>
    <div class="title-chart-1">
      303(d) list of impaired river basins measured by
      {{ checkedUnits[0] }}
    </div>
    <div class="arrow" :height="20">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1050 100">
        <defs>
          <marker
            id="arrowhead"
            markerWidth="10"
            markerHeight="7"
            refX="0"
            refY="3.5"
            orient="auto"
          >
            <polygon points="0 0, 10 3.5, 0 7" />
          </marker>
        </defs>
        <line
          x1="0"
          y1="20"
          x2="1000"
          y2="20"
          stroke="#000"
          stroke-width="2"
          marker-end="url(#arrowhead)"
        />
      </svg>
    </div>

    <div class="BoundsByBasin">
      <div class="ByBasin" v-for="(key, index) in sortedBasin" :key="key[0]">
        <!--  -->
        <transition-group name="flip-list" tag="div" class="test2">
          <div
            class="expand"
            key="testingTgrp"
            @mouseenter="hover = key[0]"
            @mouseleave="hover = null"
            v-on:mouseenter="emitToParent"
            v-on:mouseleave="emitToParent"
            :style="{
              width: xScale(key[1]) + 130 + 'px',
            }"
          >
            <div class="horizontal-title">{{ key[0] }}</div>
            <div class="horizontal-bar" style="height: 50px; overflow: none;">
              <div
                class="horizontal-title2"
                :style="{
                  width: xScale(key[1]) + 130 + 'px',
                  fill: colors[index],
                }"
              >
                {{ Math.round(key[1] * 10) / 10 }} {{ checkedUnits[0] }}
              </div>

              <svg
                class="wave2"
                viewBox="100 0 500 150"
                preserveAspectRatio="none"
                :style="{
                  height: 100 + '%',
                  width: xScale(key[1]) + 'px',
                  fill: '#227488',
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
                  backgroundColor: coloring(key2[0]),
                }"
              ></div>

              <div v-if="fromChild === key2[0]" class="Details3" :style="{}">
                <img class="icon" src="../assets/caution.png" />
              </div>
              <transition-group name="list-complete">
                <div v-if="hover === key[0]" class="Details2">
                  {{ Math.round((key2[1] / key[1]) * 10000) / 100 + "%" }}
                  {{ key2[0] }}
                </div>
              </transition-group>
            </div>
            <div
              class="horizontal-bar"
              style="height: 30px; overflow: visible;"
            >
              <svg
                viewBox="0 0 500 150"
                preserveAspectRatio="none"
                :style="{ height: 50 + 'px', width: xScale(key[1]) + 'px' }"
              >
                <path
                  d="M0.00,92.27 C216.83,192.92 304.30,8.39 500.00,109.03 L500.00,0.00 L0.00,0.00 Z"
                  :style="{ fill: '#227488' }"
                ></path>
              </svg>
            </div>
          </div>
        </transition-group>
      </div>
    </div>
  </div>
</template>

<script>
import * as d3 from "d3";

export default {
  components: {},
  name: "VueOnlyTest",
  data() {
    return {
      hover: null,
      active: false,
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
      colors2: [
        {
          cause: "Siltation",
          color: "#2828fb",
        },
        {
          cause: "Metals",
          color: "#5828fb",
        },
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
    fromChild: String,
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
    coloring() {
      let color = d3
        .scaleOrdinal()
        .range([
          "#005a32",
          "#4a1486",
          "#feedde",
          "#238b45",
          "#67000d",
          "#fdd0a2",
          "#41ab5d",
          "#636363",
          "#fdae6b",
          "#a50f15",
          "#cb181d ",
          "#ef3b2c ",
          "#fb6a4a",
          "#74c476",
          "#969696",
          "#fd8d3c",
          "#fc9272",
          "#e6550d",
          "#fcbba1",
          "#f7f7f7 ",
          "#feedde",
          "#41ab5d ",
          "#ef3b2c ",
          "#efedf5",
          "#a1d99b",
          "#ef3b2c ",
          "#ef3b2c ",
          "#dadaeb",
          "#bcbddc",
          "#f7f7f7",
          "#f7f7f7",
          "#9e9ac8",
          "#41ab5d ",
          "#cb181d",
          "#ef3b2c  ",
          "#ef3b2c  ",
          "#636363",
          "#807dba ",
          "#efedf5",
          "#6a51a3",
          "#a1d99b",
          "#252525",
          "#bdbdbd",
          "#d9d9d9 ",
        ]);
      //let color = d3.scaleOrdinal(d3.schemeSet3);
      //d3.scaleOrdinal().domain([‘A’, ‘B’, ‘C’]) .range([‘#fff’, ‘#8f8’, ‘#00f’])
      return color.domain(this.listofCauses);
    },
  },
  methods: {
    emitToParent() {
      this.$emit("hoverMain", this.hover);
    },
  },
};
</script>

<style>
.horizontal-bar {
  height: 20px;
  margin-top: 3px;
  margin-bottom: 0px;
  margin-left: 0%;
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
}
.horizontal-bar4 {
  background-color: rgb(150, 111, 134);
  margin-top: 1px;
  margin-bottom: 1px;
  margin-left: 0;
  margin-right: 100%;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.Details3 {
  position: absolute;
  margin-left: -25px;
}

.Details {
  position: inline-block;
  font-size: 50%;

  text-align: right;
  transition: all 0.3s ease;
  transition: all 0.2s ease-in-out;
  animation-name: popin;
  animation-duration: 0.2s;
  animation-timing-function: easeout;
}
.Details2 {
  font-size: 110%;
  text-align: right;
  transition: all 0.2s ease-in-out;
  animation-name: slowExpand;
  animation-duration: 0.2s;
  animation-timing-function: easeout;
}
.Details:hover > .Details2 {
  font-weight: bold;
  font-size: 160%;
  text-align: right;
  opacity: 1;

  margin-right: 2%;
}

#testpath:hover {
  cursor: pointer;
  /* height: 100px; */
  transform: scale(1, 2);
  background-color: red;
  margin-top: 15px;
}
.ByBasin {
  height: 25vh;
  display: inline-block;
  vertical-align: center;
  transform: scale(1, 1);
  margin-bottom: 0;
  margin-left: 0;
  margin-left: 0;
}
.ByBasin:hover .Details {
  max-height: 100px;
  transition-delay: 5s;
}

.Details {
  max-height: 100%;
  transition: max-height 5s;
}

.wave2 {
  position: relative;

  height: 50%;
  width: 100%;
  margin-bottom: 5%;

  animation-duration: 10s;
  animation-iteration-count: infinite;
  animation-direction: alternate-reverse;
  z-index: -1;
}
.test2 {
  margin-left: 0%;
  margin-right: 100px;
}
.horizontal-title {
  position: relative;
  width: 100%;
  margin-bottom: 0px;
  color: #111;
  font-family: "Open Sans", sans-serif;
  font-size: 26px;
  font-weight: 300;
  line-height: 32px;
  text-align: left;
}
.horizontal-title2 {
  position: absolute;
  display: inline-block;

  text-align: right;
  margin-top: 0;
  font-size: 1.4em;
}
.title-chart-1 {
  font-weight: bold;
  font-size: 26px;
  margin-bottom: 0;
  margin-left: 25%;
  text-align: left;
  width: 50vw;
}
.icon {
  height: 20px;
  width: 20px;
}
.arrow {
  height: 50px;
  margin-left: 25%;
  margin-right: 25%;
  margin-bottom: 1%;
}
.filler {
  height: 100px;
}
.BoundsByBasin {
  text-align: left;
  margin-left: 25%;
  margin-right: 20%;
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

@keyframes slowExpand {
  0% {
    transform: scale(1);
  }
  75% {
    transform: scale(1, 1.2);
    animation-timing-function: easeout;
  }
  100% {
    transform: scale(1, 1.3);
  }
}
.cls-1,
.cls-10,
.cls-11,
.cls-2,
.cls-3,
.cls-4,
.cls-5,
.cls-6,
.cls-7,
.cls-8,
.cls-9 {
  stroke: rgb(255, 255, 255);
  stroke-linecap: round;
  stroke-linejoin: round;
  stroke-width: 2px;
}
.flip-list-move {
  transition: transform 1s;
}
/* transition: max-height 0.25s ease-out; */
.list-complete-item {
  transition: all 1s;
}
.list-complete-enter,
.list-complete-leave-to {
  opacity: 0;
}
.list-complete-leave-active {
  position: inline-block;
}
</style>
