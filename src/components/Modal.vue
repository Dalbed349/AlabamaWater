<template>
  <transition name="fade">
    <div class="Modal" :style="{ display: scrollCheck }">
      <div class="container">
        <!-- <div class="scrollY">Scroll-Y is {{ scrollPosition }}</div> -->
        <!-- <div>{{ scrollCheck }}</div>
      <div>Rounded to the nearest 100: {{ scrollBlock }}</div> -->
        <!-- <div>{{ this.filters }}</div> -->
        <!-- <div class="filters">
        <el-checkbox-group v-model="filters">
          <el-checkbox label="2020"></el-checkbox>
          <el-checkbox label="2018"></el-checkbox>
          <el-checkbox label="2016"></el-checkbox>
          <el-checkbox label="2014"></el-checkbox>
          <el-checkbox label="2012"></el-checkbox>
          <el-checkbox label="2010"></el-checkbox>
          <el-checkbox label="2008"></el-checkbox>
          <el-checkbox label="2006"></el-checkbox>
          <el-checkbox label="2004"></el-checkbox>
          <el-checkbox label="2002"></el-checkbox>
          <el-checkbox label="2000"></el-checkbox>
        </el-checkbox-group>
      </div> -->

        <div class="child">
          <button type="button" name="button" v-on:click="$emit('decrease')">
            Previous
          </button>
        </div>
        <div class="child2">
          {{ filters[this.counter] }}
        </div>
        <div class="child3">
          <!-- Simplest - call `$emit()` inline-->
          <button type="button" name="button" v-on:click="$emit('increment')">
            Next
          </button>
        </div>
        <div class="item-a">
          <img alt="Vue" src="../assets/riverBasins.png" height="400" contain />
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      childMessage: "",
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
    };
  },
  name: "Modal",
  props: {
    scrollPosition: Number,
    counter: Number,
    modalYpos: Number,
  },
  computed: {
    scrollBlock() {
      return Math.floor(this.scrollPosition / 100);
    },
    scrollCheck() {
      if (
        this.scrollPosition < this.modalYpos - 90 ||
        this.scrollPosition > 4300
      ) {
        let result = "none";
        return result;
      } else {
        let result1 = "inline";
        return result1;
      }
    },
  },
  methods: {
    // emitToParent(event) {
    //   this.$emit("childToParent", this.childMessage);
    // },
  },
};
</script>

<style>
.Modal {
  position: fixed;
  top: 30vh;
  left: 0vw;
  width: 275px;
  height: 50vh;
  opacity: 1;
  margin-left: 3%;
  transform: scale(1.2, 1.2);
  /* // padding: 5px; */
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.container {
  display: grid;
  grid-template-columns: 80px auto 80px auto;
  grid-template-rows: 25% 100px 50px;
}
.scrollY {
  display: grid;
}
.child2 {
  grid-column-start: 3;
  text-align: center;

  margin-bottom: 15px;
  color: #111;
  font-family: "Open Sans", sans-serif;
  font-size: 40px;
  font-weight: 200;
  line-height: 32px;
  /* font-weight: bold; */
}
.child3 {
  grid-column-start: 5;
}
.child button {
  width: 80px;
  border-radius: 8px;
  margin-top: 30%;
  border: white;
}
.child3 button {
  width: 80px;
  border-radius: 8px;
  margin-top: 30%;
  border: white;
}
.item-a {
  display: grid;
  grid-column-start: 1;
  grid-column-end: span col4-start;
  grid-row-start: 2;
  grid-row-end: span 2;
}
</style>
