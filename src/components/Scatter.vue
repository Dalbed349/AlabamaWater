<template>
  <div class="wrapper">
    <div class="Scatter">
      <h1>D3 Scatterplot</h1>
      <div id="chart"></div>
    </div>
  </div>
</template>

<script>
import * as d3 from "d3";

export default {
  name: "Scatter",
  methods: {
    createSvg() {
      d3.csv("EditedMacroBlackWarrior.csv").then(function(data) {
        console.log(data);
        // Variables

        var margin = { top: 50, right: 50, bottom: 100, left: 50 };
        var h = 600 - margin.top - margin.bottom;
        var w = 600 - margin.left - margin.right;

        // Scales
        var x = d3.scaleLinear().range([0, w]);
        var y = d3.scaleLinear().range([h, 0]);

        // SVG
        var svg = d3
          .select("#chart")
          .append("svg")
          .attr("width", w + margin.left + margin.right)
          .attr("height", h + margin.top + margin.bottom)
          .append("g")
          .attr(
            "transform",
            "translate(" + margin.left + "," + margin.top + ")"
          );
        data.forEach(function(d) {
          d.Hqs = parseInt(d.HabitatQualityScore);
          d.Wmbia = parseInt(d.WMBIAssessmentScore);
        });

        x.domain(
          d3.extent(data, function(d) {
            return d.Hqs;
          })
        );
        y.domain([
          0,
          d3.max(data, function(d) {
            return d.Wmbia;
          }),
        ]);

        svg
          .selectAll("dot")
          .data(data)
          .enter()
          .append("circle")
          .attr("r", 5)
          .attr("cx", function(d) {
            return x(d.Hqs);
          })
          .attr("cy", function(d) {
            return y(d.Wmbia);
          })
          .style("fill", function(d) {
            return d.Year <= 2007 ? "red" : "green";
          })
          //   .on("mouseover", (event, d) => {
          //     tooltip
          //       .transition()
          //       .duration(200)
          //       .style("opacity", 0.9);
          //     tooltip
          //       .html(`${textValue(d)} \n$${yValue(d)} Billion`)
          //       .style("left", d3.event.pageX + "px")
          //       .style("top", d3.event.pageY + "px");
          //   })
          //   .on("mouseout", (d) => {
          //     tooltip
          //       .transition()
          //       .duration(500)
          //       .style("opacity", 0);
          //   });
          .on("mouseover", function(event, d) {
            tooltip.style("opacity", 1);
            tooltip
              .transition()
              .duration(200)
              .style("opacity", 0.9);
            tooltip
              .html(`${d.Year} \n${d.WMBIRating} `)
              .style("left", d3.pointer(event)[0] + "px")
              .style("top", d3.pointer(event)[1] + "px");
            console.log(d3.pointer(event)[0], "x", d3.pointer(event)[1], "y");
          })
          .on("mouseleave", function() {
            // console.log(d);
            tooltip
              .transition()
              .duration(500)
              .style("opacity", 0);
            // console.log(d3.pointer(event));
          });

        var tooltip = d3
          .select("#chart")
          .append("div")
          .attr("class", "tooltip")
          .style("opacity", 0);
        // Add the X Axis
        svg
          .append("g")
          .attr("transform", "translate(0," + h + ")")
          .call(d3.axisBottom(x));

        // Add the Y Axis
        svg.append("g").call(d3.axisLeft(y));
        svg.append("g").call(d3.axisLeft(y));

        // text label for the y axis
        svg
          .append("text")
          .attr("transform", "rotate(-90)")
          .attr("y", 0 - margin.left)
          .attr("x", 0 - h / 2)
          .attr("dy", "1em")
          .style("text-anchor", "middle")
          .text("WMB-I Bioassessment Score");
        svg
          .append("text")
          .attr(
            "transform",
            "translate(" + w / 2 + " ," + (h + margin.top + 20) + ")"
          )
          .style("text-anchor", "middle")
          .text("Habitat Quality Score");

        svg.selectAll("dot");
      });
    },
  },
  mounted() {
    this.createSvg();
  },
};
</script>

<style>
.scatter {
  margin-top: 100px;
  margin-right: 50%;
  height: 800px;
  width: 800px;
}
.axis path,
.axis line {
  fill: none;
  stroke: black;
  shape-rendering: crispEdges;
}
#chart {
  position: relative;
  height: 600px;
  width: 600px;
}
.axis text {
  font-family: sans-serif;
  font-size: 11px;
}
.tooltip {
  position: absolute;
}
.wrapper {
  margin-right: 50%;
  margin-left: 25%;
}
</style>
