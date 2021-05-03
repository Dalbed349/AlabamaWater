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
        <!-- @mouseenter="hover = key[0]"
          @mouseleave="hover = null" -->
        <!-- @mouseover="hovertrue = true"
          @mouseleave="hovertrue = false" -->
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
            :x="xScale(hovertrue)"
            :y="yScale(hovertruevalue) - 21"
            background-color="white"
            font-size=".9em"
            dy="-.5em"
            dx=".5em"
            width="100%"
            height="18"
          >
            <!-- {{ d[0] }},{{ Math.round(d[1] * 10) / 10 }} -->
          </rect>
          <text
            v-if="hovertrue"
            class="testingya"
            fill="steelblue"
            :x="xScale(hovertrue)"
            :y="yScale(hovertruevalue)"
            background-color="#000"
            font-size=".9em"
            dy="-.5em"
            dx=".5em"
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
      svgHeight: 300,
      svgWidth: 370,
      margin: { top: 50, left: 60, bottom: 70, right: 10 },
      hovertrue: null,
      hovertruevalue: null,
      hover: null,
    };
  },
  components: {
    // tooltip,
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
      // console.log(axisSelection);
      //if(axisSelection === ‘y’){ g.append(‘text’)     .attr(‘transform’, ‘rotate(90)’)     .text(‘Y AXIS’)}
      // .transition()
      const g = d3.select(el);
      g
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
          .attr("y", 10)
          .attr("x", 2)
          .attr("dx", "1em")
          .attr("dy", "-.5em")
          .attr("transform", "rotate(80)")
          //.attr("transform", "translate(2,0)")
          .style("text-anchor", "start")
          .style("font", "9px times");

        // var tooltip = d3
        //   .select(".CauseMultiples")
        //   .append("div")
        //   .attr("class", "tooltip")
        //   .style("opacity", 1);

        // g.selectAll(".bars")
        //   .data(this.rollupByCause)
        //   .enter()
        //   .on("mouseover", function(event, d) {
        //     console.log(d[0]);
        //     tooltip.style("opacity", 1);
        //     // tooltip
        //     //   .transition()
        //     //   .duration(200)
        //     //   .style("opacity", 0.9);
        //     tooltip
        //       // .html(`${d[1]} `)
        //       .html("hello")
        //       .style("left", d3.pointer(event)[0] + "px")
        //       .style("top", d3.pointer(event)[1] + "px");
        //     // .style("left", 10 + "px")
        //     // .style("top", 10 + "px");
        //     // .style("height", 50)
        //     // .style("width", 50);
        //     console.log(d3.pointer(event)[0], "x", d3.pointer(event)[1], "y");
        //   });
        // .on("mouseleave", function() {
        //   // console.log(d);
        //   tooltip
        //     .transition()
        //     .duration(500)
        //     .style("opacity", 0);
        //   // console.log(d3.pointer(event));
        // });
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
  overflow: visible;
}

.CauseMultiples p {
  height: 1 vh;
  margin-top: 1%;
  position: absolute;
  margin-left: 30px;
}
.testingya {
  background-color: red;
}

/* .barwithtooltip:hover text {
  opacity: 1;
} */
.bars:hover {
  fill: brown;
}
.tooltip {
  position: absolute;
  height: 10px;
}
</style>
