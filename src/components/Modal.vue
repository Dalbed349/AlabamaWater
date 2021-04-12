<template>
  <div class="Modal" :style="{ display: scrollCheck }">
    <!-- <div>Scroll-Y is {{ scrollPosition }}</div>
    <div>{{ scrollCheck }}</div>
    <div>Rounded to the nearest 100: {{ scrollBlock }}</div> -->
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
  methods: {},
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
