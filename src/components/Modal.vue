<template>
  <div class="Modal" :style="{ display: scrollCheck }">
    <!-- <div>Scroll-Y is {{ scrollPosition }}</div>
    <div>{{ scrollCheck }}</div>
    <div>Rounded to the nearest 100: {{ scrollBlock }}</div> -->
    <div class="filters">
      <el-checkbox-group v-model="filters" @change="onChange(selectedMonth)">
        <el-checkbox
          label="2020"
          :key="month"
          :selected="selectedMonth === month"
        ></el-checkbox>
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
    </div>
    <img
      alt="Vue"
      src="../assets/riverBasins.png"
      height="400"
      style="vertical-align:middle;margin:10px 0px"
      contain
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      filters: [
        "2020",
        "2018",
        "2016",
        "2014",
        "2012",
        "2010",
        "2008",
        "2006",
        "2004",
        "2002",
        "2000",
      ],
    };
  },
  name: "Modal",
  props: {
    scrollPosition: Number,
  },
  computed: {
    scrollBlock() {
      return Math.floor(this.scrollPosition / 100);
    },
    scrollCheck() {
      if (this.scrollPosition < 600 || this.scrollPosition > 4300) {
        let result = "none";
        return result;
      } else {
        let result1 = "inline";
        return result1;
      }
    },
  },
  methods: {
    onChange(newYear) {
      this.$emit("change", newYear);
    },
  },
};
</script>

<style>
.Modal {
  position: fixed;
  top: 30vh;
  left: 0vw;
  width: 20vw;
  height: 50vh;
  opacity: 1;

  padding: 5px;
}
</style>
