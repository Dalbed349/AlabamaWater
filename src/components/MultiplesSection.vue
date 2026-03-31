<template>
  <div class="viz2Wrapper">
    <h2>Causes and Sources of Impairment</h2>
    <img id="industry" src="../assets/industry.svg" />
    <div class="viz2details">
      <!-- NEW COMPONENT -->
      <div class="filters" id="viz2filters">
        <div class="checkbox-group">
          <label
            @mousedown="$emit('removeOtherUnit')"
            v-for="unit in units"
            :key="unit"
            class="native-checkbox"
          >
            <input
              type="checkbox"
              :value="unit"
              :checked="checkedUnits.includes(unit)"
              @change="updateUnits(unit, $event.target.checked)"
            />
            <span class="checkbox-label">{{ unit }}</span>
          </label>
        </div>
      </div>
      <StackedSideBar
        :checkedUnits="checkedUnits"
        :data="filteredSmallMultiples"
        :basin="hoverSecondVis"
        :cause="hoverSecondVisCause"
        v-on:increment="$emit('increment')"
        v-on:decrease="$emit('decrease')"
        :counter="counter"
      ></StackedSideBar>
    </div>
    <div class="viz2Wrapper2">
      <div class="viz2">
        <CauseMultiples
          v-for="key in sortedBasin"
          :key="key[0]"
          :data="filteredSmallMultiples"
          :basin="key[0]"
          v-on:hoverSecondVis="$emit('hoverSecondVis', $event)"
          v-on:hoverSecondVisCause="$emit('hoverSecondVisCause', $event)"
        >
        </CauseMultiples>
      </div>
    </div>
  </div>
</template>

<script>
import StackedSideBar from "./StackedSideBar.vue";
import CauseMultiples from "./CauseMultiples.vue";

export default {
  name: "MultiplesSection",
  components: {
    StackedSideBar,
    CauseMultiples,
  },
  props: {
    checkedUnits: Array,
    units: Array,
    filteredSmallMultiples: Array,
    hoverSecondVis: String,
    hoverSecondVisCause: String,
    counter: Number,
    sortedBasin: Array,
  },
  methods: {
    updateUnits(unit, isChecked) {
      let newUnits = [...this.checkedUnits];
      if (isChecked) {
        if (!newUnits.includes(unit)) newUnits.push(unit);
      } else {
        newUnits = newUnits.filter(u => u !== unit);
      }
      this.$emit('update:checkedUnits', newUnits);
    }
  }
};
</script>

<style scoped>
.viz2Wrapper {
  display: inline-block;
  margin-right: 0%;
  margin-top: 5%;
  margin-bottom: 7%;
  margin-left: 0%;
}
.viz2Wrapper h2 {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 3em;
  margin-bottom: 1%;
  margin-left: 3%;
}
#industry {
  position: sticky;
  margin-top: -5%;
  margin-right: 78%;
  margin-bottom: -0.8%;
  width: 19.99vw;
  z-index: -1;
}
.viz2details {
  position: absolute;
  margin-left: 1%;
  z-index: 0;
  width: 20vw;
  height: 90%;
  border-radius: 15px;
  background-color: #5696bc;
  opacity: 1;
}
.filters {
  position: relative;
  text-align: center;
}
.native-checkbox {
  display: inline-block;
  margin: 5px 10px;
  cursor: pointer;
  font-family: -apple-system, sans-serif;
  font-size: 14px;
  color: #fff;
}
.native-checkbox input {
  margin-right: 5px;
}
#viz2filters {
  margin-right: 0;
  margin-bottom: 0px;
  margin-left: 0;
}
.viz2Wrapper2 {
  display: inline-block;
  margin-right: 0%;
  margin-top: -1%;
  margin-bottom: 2%;
  margin-left: 20%;
}
.viz2 {
  display: grid;
  grid-template-rows: repeat(5);
  grid-template-columns: repeat(4, auto);
}
</style>
