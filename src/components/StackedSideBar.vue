<template>
  <div id="container" class="svg-container" align="center">
    <div class="box" v-for="key in rollupByCauseTEST" :key="key">
      <div
        class="legend1"
        :style="{
          height: 100 + 'px',
          width: 20 + 'px',

          position: 'absolute',
        }"
      ></div>
      <div class="detailsmod">{{ key[1] }}</div>
    </div>
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
  },

  data: () => ({
    svgWidth: 0,
  }),
  methods: {
    basinNull() {
      if (this.basin == null) {
        let g = this.basin == "Black Warrior";
        return g;
      }
    },
    causeNull() {
      if (this.cause == null) {
        let g = this.cause == "Nutrients";
        return g;
      }
    },
  },

  computed: {
    // rollupByCauseTEST() {
    //   return d3.rollups(
    //     this.data.filter(
    //       (d) =>
    //         this.cause.includes(d.Causes) && this.basin.includes(d.RiverBasin),
    //       (values) => d3.sum(values.map((d) => +d.Size)),
    //       (d) => d.Sources
    //     )
    //   );
    // },
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
      return this.data.filter(
        (d) =>
          this.cause.includes(d.Causes) && this.basin.includes(d.RiverBasin),
        (values) => d3.sum(values.map((d) => +d.Size)),
        (d) => d.Sources
      );
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
  height: 100%;
  padding-bottom: 1%;
  vertical-align: top;
  overflow: hidden;
}
.box {
  height: auto;
}
</style>
