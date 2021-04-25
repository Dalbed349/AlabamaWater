<template>
  <transition name="fade">
    <div
      class="ModalLegend"
      :style="{ display: scrollCheck[0], opacity: scrollopacity[0] }"
    >
      <div class="container1" v-on:click="emitToParent">
        <div class="box" v-for="key in listOfCausesFiltered" :key="key">
          <div
            class="legend1"
            @mouseenter="hoverValue = key"
            @mouseleave="hoverValue = null"
            v-on:mouseenter="emitToParent"
            :style="{
              height: 2.0 + 'vh',
              width: 20 + 'px',
              backgroundColor: coloring(key),
              float: 'left',
            }"
          ></div>
          <div class="detailsmod">{{ key }}</div>
        </div>
        <!-- <div
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
        </div> -->
      </div>
    </div>
  </transition>
</template>

<script>
import * as d3 from "d3";
export default {
  data() {
    return {
      hoverValue: null,
    };
  },
  name: "ModalLegend",
  props: {
    scrollPosition: Number,
    counter: Number,
    modalYpos: Number,
    listofCauses: Array,
    listOfCausesFiltered: Array,
    modalYposEnd: Number,
  },
  computed: {
    scrollBlock() {
      return Math.floor(this.scrollPosition / 100);
    },
    scrollCheck() {
      if (
        this.scrollPosition < this.modalYpos - 190 ||
        this.scrollPosition > this.modalYposEnd
      ) {
        let result = "none";

        return [result];
      } else {
        let result = "inline";

        return [result];
      }
    },
    scrollopacity() {
      if (
        this.scrollPosition < this.modalYpos - 90 ||
        this.scrollPosition > this.modalYposEnd - 100
      ) {
        let result = 0;

        return [result];
      } else {
        let result = 1;

        return [result];
      }
    },
    coloring() {
      // let color = d3.scaleOrdinal(d3.schemeCategory10);
      //let color = d3.interpolator(d3.interpolatePuRd);
      let color = d3.scaleOrdinal(d3.schemeSet3);
      // .range(d3.schemeSet3);

      //d3.scaleOrdinal().domain([‘A’, ‘B’, ‘C’]) .range([‘#fff’, ‘#8f8’, ‘#00f’])
      console.log(this.listofCauses);
      return color.domain(this.listofCauses);
    },
  },
  methods: {
    emitToParent() {
      this.$emit("childToParent", this.hoverValue);
    },
  },
};
</script>

<style>
.ModalLegend {
  position: fixed;
  top: 30vh;
  left: 90vw;
  width: 150px;
  height: 0;
  opacity: 1;
  margin-left: 0%;
  transform: scale(1.2, 1.2);
  /* // padding: 5px; */
  visibility: visible;
  -webkit-transition: opacity 1s ease-out;
  -moz-transition: opacity 1s ease-out;
  -o-transition: opacity 1s ease-out;
  transition: opacity 1s ease-out;
  opacity: 1;
}
.lengend1 {
}
.box {
  overflow: hidden;
  height: 20px;
}

.detailsmod {
  text-align: left;
  float: left;
  font-size: 10px;
  overflow: hidden;
  margin-left: 1%;
}
</style>
