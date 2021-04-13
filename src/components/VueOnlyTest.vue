<template>
  <div class="VueOnlyTest">
    <div class="title-chart-1">
      303(d) list of impaired waterbasins by size {{ checkedUnits }}
    </div>

    <!-- 
      
    <transition-group name="fade"> -->
    <div class="ByBasin" v-for="(key, index) in sortedBasin" :key="key[0]">
      <!--  -->
      <div
        class="test2"
        @mouseenter="hover = true"
        @mouseleave="hover = false"
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
        <!-- @mouseleave="hover = false" -->
        <!-- @mouseover="hover = true" -->
        <div
          class="Details"
          v-for="(key2, index2) in FinalByBasin2.get(key[0])"
          :key="key2"
        >
          <div
            class="horizontal-bar4"
            :style="{
              height: (key2[1] / key[1]) * 100 + 'px',
              width: xScale(key[1]) + 'px',
              backgroundColor: colors[index2],
            }"
          ></div>

          <!-- colors[index] -->
          <div v-if="hover" class="Details2" :style="{ display: 'inline' }">
            {{ Math.round((key2[1] / key[1]) * 1000) / 10 + "%" }}
            {{ key2[0] }}
          </div>
          <!-- {{ (key2[1] / key[1]) * 100 }} -->
        </div>

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
      </div>
      <!-- </div> -->
    </div>
    <!-- </transition-group> -->
  </div>
</template>

<script>
import * as d3 from "d3";

export default {
  components: {},
  name: "VueOnlyTest",
  data() {
    return {
      hover: false,
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
    // mouseOver: function() {
    //   this.active = !this.active;
    // },
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
  /* margin-left: 25%;
  margin-right: 100%; */
}
.horizontal-bar4 {
  background-color: rgb(150, 111, 134);
  margin-top: 1px;
  margin-bottom: 1px;
  margin-left: 0;
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
  /* position: inline-block; */
  font-size: 100%;
  text-align: right;
  /* transition: all 0.3s ease; */
  /* transition: all 0.2s ease-in-out; */
  /* animation-name: slowExpand;
  animation-duration: 2s;
  animation-timing-function: easeout; */
  transition: all 0.2s ease-in-out;
  animation-name: slowExpand;
  animation-duration: 0.2s;
  animation-timing-function: easeout;
}
.Details:hover > .Details2 {
  font-size: 150%;
  text-align: right;
  opacity: 1;
  margin-right: 5%;
}
/* .Details2.transReset {
  transition: intial;
} */
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
.ByBasin {
  transform: scale(1, 1);
  margin-bottom: 2%;
  margin-left: 25vw;
  background: white;
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
.test2 {
  margin-left: 0%;
  margin-right: 0%;
}
.horizontal-title {
  position: relative;

  margin-bottom: 15px;
  color: #111;
  font-family: "Open Sans", sans-serif;
  font-size: 30px;
  font-weight: 300;
  line-height: 32px;
  text-align: left;
}
.horizontal-title2 {
  position: absolute;
  display: inline-block;
  /* width: 100%; */
  text-align: right;
  margin-top: 0;
  font-size: 1.1em;
}
.title-chart-1 {
  font-weight: bold;
  margin-bottom: 50px;
}
.filler {
  height: 100px;
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

/* @keyframes popin {
  0% {
    transform: scale(0.2);
  }
  75% {
    transform: scale(2.2);
    animation-timing-function: easeout;
  }
  100% {
    transform: scale(1);
  }
} */
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
</style>
