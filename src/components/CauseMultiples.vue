<template>
  <div
    class="CauseMultiples"
    @mouseenter="hover = basin"
    @mouseleave="hover = null"
    v-on:mouseenter="emitToParent"
  >
    <p>{{ basin }}</p>
    <svg :width="svgWidth" :height="svgHeight">
      <g
        class="barwithtooltip"
        :transform="'translate(' + margin.left + ',' + margin.top + ')'"
      >
        <rect
          v-on:mouseenter="emitToParent"
          class="bars"
          v-for="(d, i) in rollupByCause"
          :key="i"
          :width="xScale.bandwidth()"
          :height="height - yScale(d[1])"
          fill="steelblue"
          :x="xScale(d[0])"
          :y="yScale(d[1])"
          @mouseover="(hovertrue = d[0]), (hovertruevalue = d[1])"
          @mouseleave="(hovertrue = null), (hovertruevalue = null)"
        ></rect>
        <g>
          <rect
            v-if="hovertrue"
            fill="white"
            :x="xScale(hovertrue) - adjustAnchor()"
            :y="yScale(hovertruevalue) - 21"
            background-color="white"
            font-size=".9em"
            dy="-.5em"
            dx=".5em"
            width="50%"
            height="18"
          ></rect>
          <text
            v-if="hovertrue"
            class="testingya"
            fill="steelblue"
            :x="xScale(hovertrue)"
            :y="yScale(hovertruevalue)"
            font-size=".9em"
            dy="-.5em"
            dx=".5em"
            :text-anchor="textAnchor()"
          >
            {{ hovertrue }},{{ Math.round(hovertruevalue * 10) / 10 }}
          </text>
        </g>
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
      svgHeight: 330,
      svgWidth: 370,
      margin: { top: 60, left: 60, bottom: 70, right: 20 },
      hovertrue: null,
      hovertruevalue: null,
      hover: null,
    };
  },
  components: {},
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

    rollupByCause() {
      return d3.rollups(
        this.data.filter((d) => d.RiverBasin == this.basin),
        (values) => d3.sum(values.map((d) => +d.Size)),
        (d) => d.Causes
      );
    },
    rollupByCauseTEST() {
      return d3.rollups(
        this.data.filter((d) => d.RiverBasin == this.basin),
        (values) => d3.sum(values.map((d) => +d.Size)),
        (d) => d.Causes,
        (d) => d.Sources
      );
    },
  },
  methods: {
    hovertrue1() {
      this.hovertrue = true;
    },
    textAnchor() {
      if (this.xScale(this.hovertrue) > this.svgWidth / 2 - 30) {
        return "end";
      } else {
        return "start";
      }
    },
    adjustAnchor() {
      if (this.xScale(this.hovertrue) > this.svgWidth / 2) {
        return 140;
      } else {
        return 0;
      }
    },
    emitToParent() {
      this.$emit("hoverSecondVis", this.hover);
      this.$emit("hoverSecondVisCause", this.hovertrue);
      console.log(this.hovertrue);
    },
  },
  directives: {
    axis(el, binding) {
      const axisSelection = binding.arg; // either X or Y
      const axisMethod = { x: "axisBottom", y: "axisLeft" }[axisSelection];
      const methodArg = binding.value; // the scale passed to this directive
      //////v-{directiveName}:{binding.arg}=“{binding.value}”
      ///// d3.select(‘g.x-axis’).call(g => yAxis(g))

      //if(axisSelection === ‘y’){ g.append(‘text’)     .attr(‘transform’, ‘rotate(90)’)     .text(‘Y AXIS’)}
      // .transition()
      const g = d3.select(el);
      g
        //Line 92 ==> .call(d3[“axisBottom”](xScale))
        .call(d3[axisMethod](methodArg));
      if (axisSelection === "x") {
        g.selectAll("text")
          .attr("y", 10)
          .attr("x", 2)
          .attr("dx", "1em")
          .attr("dy", "-.5em")
          .attr("transform", "rotate(80)")
          .style("text-anchor", "start")
          .style("font", "9px times");
      }
    },
  },
};
</script>
<style>
.CauseMultiples {
  overflow: visible;
}
.CauseMultiples p {
  height: 1 vh;
  margin-top: 1%;
  position: absolute;
  margin-left: 30px;
}
.testingya {
}
.bars:hover {
  fill: brown;
}
.tooltip {
  position: absolute;
  height: 10px;
}
</style>
