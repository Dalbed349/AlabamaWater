<template>
  <div class="CauseMultiples">
    <p>{{ basin }}</p>
    <svg :width="svgWidth" :height="svgHeight">
      <g
        class="barwithtooltip"
        :transform="'translate(' + margin.left + ',' + margin.top + ')'"
      >
        <rect
          class="bars"
          v-for="(d, i) in rollupByCause"
          :key="i"
          :width="xScale.bandwidth()"
          :height="height - yScale(d[1])"
          fill="steelblue"
          :x="xScale(d[0])"
          :y="yScale(d[1])"
        ></rect>
        <text
          class="testingya"
          v-for="(d, i) in rollupByCause"
          :key="i"
          fill="steelblue"
          :x="xScale(d[0])"
          :y="yScale(d[1])"
        >
          {{ d[0] }},{{ Math.round(d[1] * 10) / 10 }}
        </text>

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
      svgHeight: 300,
      svgWidth: 350,
      margin: { top: 50, left: 40, bottom: 70, right: 10 },
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
      // .nice();
    },

    yScale() {
      return d3
        .scaleLinear()
        .domain(d3.extent(this.rollupByCause, (d) => d[1]))
        .range([this.height, 0])
        .nice();
    },
    colorScale() {
      return d3
        .scaleBand()
        .domain(d3.extent(this.rollupByCause, (d) => d[1]))
        .range(["red", "orange", "green", "blue"]);
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

      //////v-{directiveName}:{binding.arg}=“{binding.value}”
      ///// d3.select(‘g.x-axis’).call(g => yAxis(g))
      // console.log(axisSelection);
      //if(axisSelection === ‘y’){ g.append(‘text’)     .attr(‘transform’, ‘rotate(90)’)     .text(‘Y AXIS’)}

      const g = d3.select(el);
      g.transition()
        //Line 92 ==> .call(d3[“axisBottom”](xScale))
        .call(d3[axisMethod](methodArg));
      if (axisSelection === "x") {
        // g.selectAll("text")
        //   .attr("transform", "rotate(80)")
        // .style("text-anchor", "start")
        //.style("font", "2px times");
        // .attr("x", 7);
        // .text("X AXIS");
        g.selectAll("text")
          .attr("y", 0)
          .attr("x", 2)
          .attr("dx", "1em")
          .attr("dy", "-.5em")
          .attr("transform", "rotate(80)")
          //.attr("transform", "translate(2,0)")
          .style("text-anchor", "start")
          .style("font", "8px times");
      }
    },
  },
};

// .selectAll("text")
// .attr("y", 0)
// .attr("x", 9)
// .attr("dy", ".35em")
// .attr("transform", "rotate(80)")
// .style("text-anchor", "start")
// .style("font", "10px times");
</script>

<style>
.CauseMultiples {
}

.CauseMultiples p {
  height: 1 vh;
  margin-top: 2%;
}
.testingya {
  opacity: 0;
}
/* .testingya:hover {
  opacity: 1;
} */
/* .bars:hover ~ .testingya {
  opacity: 1;
} */
.barwithtooltip:hover text {
  opacity: 1;
}
.bars:hover {
  fill: brown;
}
</style>
