<template>
  <div class="CauseMultiples">
    <p>{{ basin }}</p>
    <svg :width="svgWidth" :height="svgHeight">
      <g :transform="'translate(' + margin.left + ',' + margin.top + ')'">
        <rect
          v-for="(d, i) in rollupByCause"
          :key="i"
          :width="xScale.bandwidth()"
          :height="height - yScale(d[1])"
          fill="red"
          :x="xScale(d[0])"
          :y="yScale(d[1])"
        />

        <!-- axis -->
        <g v-axis:x="xScale" :transform="`translate(0, ${height})`"></g>
        <g v-axis:y="yScale"></g>
      </g>
    </svg>
  </div>
</template>

<script>
import * as d3 from "d3";

export default {
  name: "CauseMultiples",
  data() {
    return {
      svgHeight: 500,
      svgWidth: 500,
      margin: { top: 100, left: 100, bottom: 100, right: 100 },
    };
  },

  props: {
    data: Array,
    basin: String,
  },
  computed: {
    width() {
      return this.svgWidth - this.margin.left - this.margin.right;
    },
    height() {
      return this.svgHeight - this.margin.top - this.margin.bottom;
    },
    xScale() {
      return d3
        .scaleBand()
        .domain(this.data.map((d) => d.Causes))
        .range([0, this.width]);
    },
    //   xScale() {
    //   return d3
    //     .scaleBand()
    //     .domain(this.rollupByCause.map((d) => d[0]))
    //     .range([0, this.width]);
    // },
    yScale() {
      return d3
        .scaleLinear()
        .domain(d3.extent(this.rollupByCause, (d) => d[1]))
        .range([this.height, 0]);
    },
    rollupByCause() {
      return d3.rollups(
        this.data.filter((d) => d.RiverBasin == this.basin),
        (values) => d3.sum(values.map((d) => +d.Size)),
        (d) => d.Causes
      );
    },
  },
  methods: {},
  directives: {
    axis(el, binding) {
      const axisSelection = binding.arg; // either X or Y
      const axisMethod = { x: "axisBottom", y: "axisLeft" }[axisSelection];
      const methodArg = binding.value; // the scale passed to this directive

      d3.select(el)
        .transition()
        .call(d3[axisMethod](methodArg));
    },
  },
};
</script>

<style></style>
