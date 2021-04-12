<template>
  <div id="container" class="svg-container" align="center">
    <h1>{{ title }}</h1>
    <svg v-if="redrawToggle === true" :width="svgWidth" :height="svgHeight">
      <g>
        <rect
          v-for="item in data"
          class="bar-positive"
          :key="item[xKey]"
          :x="xScale(item[xKey])"
          :y="yScale(0)"
          :width="xScale.bandwidth()"
          :height="0"
        ></rect>
      </g>
    </svg>
  </div>
</template>

<script>
import { scaleLinear, scaleBand } from "d3-scale";
import { max, min } from "d3-array";
// import { selectAll } from "d3-selection";
//import { transition } from "d3-transition";

//  import * as d3 from 'd3'

export default {
  name: "BarChart",
  props: {
    title: String,
    xKey: String,
    yKey: String,
    data: Array,
  },
  mounted() {
    this.svgWidth = document.getElementById("container").offsetWidth * 0.75;
    this.AddResizeListener();
    // this.AnimateLoad();
  },
  data: () => ({
    svgWidth: 0,
    redrawToggle: true,
  }),
  methods: {
    // AnimateLoad() {
    //   selectAll("rect")
    //     .data(this.data)
    //     .transition()
    //     .delay((d, i) => {
    //       return i * 150;
    //     })
    //     .duration(1000)
    //     .attr("y", (d) => {
    //       return this.yScale(d[this.yKey]);
    //     })
    //     .attr("height", (d) => {
    //       return this.svgHeight - this.yScale(d[this.yKey]);
    //     });
    // },
    AddResizeListener() {
      // redraw the chart 300ms after the window has been resized
      window.addEventListener("resize", () => {
        this.$data.redrawToggle = false;
        setTimeout(() => {
          this.$data.redrawToggle = true;
          this.$data.svgWidth =
            document.getElementById("container").offsetWidth * 0.75;
          // this.AnimateLoad();
        }, 300);
      });
    },
  },
  computed: {
    //      FinalByBasin(){
    //             if (!this.Final) {
    //             return new Map()
    //         }                                                                      // first key  can chain more , d.key1, d => d.key2, ...)
    //     let g = d3.rollup(this.Final,values => d3.mean(values.map( d => +d["Size"])),d => d["RiverBasin"])

    // // sortedG = g.slice().sort((a, b) => d3.descending(a.votes, b.votes))

    // // d3.rollup(data, values => values, d => d.key1, d => d.key2, ...)
    //                     return g
    //  },
    dataMax() {
      return max(this.data, (d) => {
        return d[this.yKey];
      });
    },
    dataMin() {
      return min(this.data, (d) => {
        return d[this.yKey];
      });
    },
    xScale() {
      return scaleBand()
        .rangeRound([0, this.svgWidth])
        .padding(0.1)
        .domain(
          this.data.map((d) => {
            return d[this.xKey];
          })
        );
    },
    yScale() {
      return scaleLinear()
        .rangeRound([this.svgHeight, 0])
        .domain([this.dataMin > 0 ? 0 : this.dataMin, this.dataMax]);
    },
    svgHeight() {
      return this.svgWidth / 1.61803398875; // golden ratio
    },
  },
};
</script>

<style scoped>
.bar-positive {
  fill: steelblue;
  transition: r 0.2s ease-in-out;
}

.bar-positive:hover {
  fill: brown;
}

.svg-container {
  display: inline-block;
  position: relative;
  width: 100%;
  padding-bottom: 1%;
  vertical-align: top;
  overflow: hidden;
}
</style>
