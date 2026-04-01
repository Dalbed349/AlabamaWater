<template>
  <div class="viz2Wrapper">
    <div class="header-multiples">
      <h2>Causes and Sources of Impairment</h2>
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
    </div>
    
    <!-- Responsive Container for Small Multiples -->
    <div class="viz2Wrapper2">
      <div class="viz2">
        <CauseMultiples
          v-for="key in sortedBasin"
          :key="key[0]"
          :data="filteredSmallMultiples"
          :basin="key[0]"
          v-on:hoverSecondVis="$emit('hoverSecondVis', $event)"
          v-on:hoverSecondVisCause="$emit('hoverSecondVisCause', $event)"
        />
      </div>
    </div>

    <!-- Side Modal for StackedSideBar (shows when a basin is hovered) -->
    <transition name="slide-fade">
      <div class="viz2details-modal" v-if="hoverSecondVis">
        <div class="modal-content">
          <button class="close-btn" @click="$emit('hoverSecondVis', null)">✕</button>
          <h3>Sources for: {{ hoverSecondVis }} Basin</h3>
          <StackedSideBar
            :checkedUnits="checkedUnits"
            :data="filteredSmallMultiples"
            :basin="hoverSecondVis"
            :cause="hoverSecondVisCause"
            v-on:increment="$emit('increment')"
            v-on:decrease="$emit('decrease')"
            :counter="counter"
          />
        </div>
      </div>
    </transition>
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
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 5% auto 10% auto;
  max-width: 1400px;
  position: relative;
  min-height: 80vh;
}
.header-multiples {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 5%;
  margin-bottom: 2%;
}
.header-multiples h2 {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: clamp(2rem, 4vw, 3em);
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
  font-size: 16px;
  font-weight: 500;
  color: #333;
}
.native-checkbox input {
  margin-right: 5px;
}
.viz2Wrapper2 {
  width: 90%;
  margin: 0 auto;
}
.viz2 {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 30px;
  justify-items: center;
  width: 100%;
}

/* Side Modal Styles */
.viz2details-modal {
  position: fixed;
  top: 10%;
  right: 0;
  width: 400px;
  max-width: 90vw;
  height: 80vh;
  background-color: #f8fcfd;
  box-shadow: -5px 0 25px rgba(0,0,0,0.2);
  z-index: 1000;
  border-top-left-radius: 15px;
  border-bottom-left-radius: 15px;
  padding: 20px;
  overflow-y: auto;
}
.modal-content {
  position: relative;
  height: 100%;
  display: flex;
  flex-direction: column;
}
.modal-content h3 {
  font-size: 1.5rem;
  margin-bottom: 10px;
  color: #333;
  border-bottom: 2px solid #5696bc;
  padding-bottom: 10px;
}
.close-btn {
  position: absolute;
  top: -10px;
  right: -5px;
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  color: #aaa;
}
.close-btn:hover {
  color: #333;
}

/* Transitions */
.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}
.slide-fade-leave-active {
  transition: all 0.3s ease-in;
}
.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(100%);
  opacity: 0;
}
</style>
