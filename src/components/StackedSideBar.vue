<template>
  <div id="container" class="svg-container" align="center">
    <div class="child">
      <button type="button" name="button" v-on:click="$emit('decrease')">
        {{ filters[counter - 1] }}
      </button>
    </div>
    <div class="child2">
      {{ filters[counter] }}
    </div>
    <div class="child3">
      <button type="button" name="button" v-on:click="$emit('increment')">
        {{ filters[counter + 1] }}
      </button>
    </div>
    <div class="info">
      Sources of {{ cause }} pollution in {{ basin }} river basin.
    </div>
    <div class="info2">
      Mouse over one of the bars in the charts to the right for a breakdown of
      the source for that contamination.
    </div>
    <transition-group name="fade1">
      <div class="box2" v-for="key in test" :key="key">
        <div
          class="legend1"
          :style="{
            height: yScale(key[1]) + 2 + 'px',
            width: 100 + '%',
            backgroundColor: coloring(key[1]),
          }"
        >
          <div
            class="detailsmod"
            :style="{ height: yScale(key[1]) + 2 + 'px' }"
            v-on:mousedown="logit()"
          >
            <p>{{ key[0] }} : {{ Math.round(key[1] * 10) / 10 }} mi</p>
          </div>
        </div>
      </div>
    </transition-group>
  </div>
</template>

<script>
import * as d3 from "d3";
// import { transition } from "d3-transition";
export default {
  name: "StackedBar",
  props: {
    data: Array,
    basin: String,
    cause: String,
    counter: Number,
  },

  data: () => ({
    svgWidth: 0,
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
  }),
  methods: {
    logit() {
      console.log(this.yScale2(50));
    },
    basinNull() {
      if (this.basin === "null") {
        return this.basin === "Black Warrior";
      }
    },
    causeNull() {
      if (this.cause === "null") {
        return this.cause === "Nutrients";
      }
    },
  },

  computed: {
    rollupByCauseTEST() {
      return d3.rollups(
        this.data.filter((d) => d.RiverBasin == this.basin),
        (values) => d3.sum(values.map((d) => +d.Size)),
        (d) => d.Causes === this.cause,
        (d) => d.Sources
      );
    },
    filteredFinal() {
      if (!this.data) {
        return null;
      }
      if (this.cause == null) {
        return this.cause === "Nutrients";
      }
      if (this.basin === null) {
        return this.basin === "Black Warrior";
      }
      return this.data.filter(
        (d) => this.cause === d.Causes && this.basin.includes(d.RiverBasin),
        (values) => d3.sum(values.map((d) => +d.Size)),
        (d) => d.Sources
      );
    },
    FinalByBasinSide() {
      if (!this.filteredFinal) {
        return new Map();
      } // first key  can chain more , d.key1, d => d.key2, ...)
      let g = d3.rollup(
        this.filteredFinal,
        (values) => d3.sum(values.map((d) => +d["Size"])),
        (d) => d["Sources"]
      );
      return g;
    },
    totalval() {
      let sum = 0;
      this.test.forEach(function(item) {
        sum += parseFloat(item[1]);
      });
      console.log(window.innerHeight - window.innerHeight * 0.2);
      return sum;
    },
    test() {
      let g = Array.from(this.FinalByBasinSide);
      //   return g;
      var f = g.sort(function(b, a) {
        return b[1] - a[1];
      });
      return f;
    },
    yScale() {
      return d3
        .scaleLinear()
        .domain([0, this.totalval])
        .range([25, window.innerHeight - 715]);
    },
    coloring() {
      //        .domain([0, 814])
      // let color = d3.scaleOrdinal(d3.schemeCategory10);
      //let color = d3.interpolator(d3.interpolatePuRd);
      //let color = d3.scaleSequential(d3.interpolateBlues);
      // .range(d3.schemeSet3);
      // .domain([0, 10000]);
      var color = d3
        .scaleSequential(d3.interpolateBlues)
        .domain([0, this.totalval * 2]);
      console.log(color(50));
      //d3.scaleOrdinal().domain([‘A’, ‘B’, ‘C’]) .range([‘#fff’, ‘#8f8’, ‘#00f’])

      return color;
    },
  },
};
</script>

<style scoped>
.svg-container {
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
.detailsmod {
  position: absolute;
  font-size: 12px;
  text-align: left;
  color: black;
  /* font-size: 1.2vh; */
  overflow: visible;
  display: flex;
  align-items: center;
  font-weight: bold;
  /* margin-left: 50%; */
  /* margin: auto; */
}
.legend1 {
  border-width: 0.1px;
  border-style: solid;
  border-radius: 5px;
  border-color: "coral";
  z-index: 1;
}
.box2 {
  text-align: left;
}
.child {
  display: inline-block;
}
.child2 {
  display: inline-block;
  margin-left: 10px;
  margin-right: 10px;
  font-style: bold;
}
.child3 {
  display: inline-block;
}
.info {
  margin-bottom: 10px;
  color: black;
  font-size: 18px;
}
.info2 {
  position: absolute;
  margin-top: 100%;
  z-index: -1;
  margin-left: 2%;
  margin-right: 2%;
  /* text-align: center; */
}
.detailsmod p {
  /* position: absolute; */
  top: 50%;
}

.fade1-enter-active {
  transition: opacity 0.2s;
}
.fade1-leave-active {
  transition: opacity 0.1s;
}
.fade1-enter {
  opacity: 0;
}
.fade1-leave-to {
  opacity: 1;
}
</style>
