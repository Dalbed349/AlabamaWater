<template>
  <div class="map2">
    <h1>The River Basins of Alabama</h1>
    <img alt="Vue" src="../assets/riverBasins.png" />
    <div class="transbox2">
      <p>
        Since 1998 stricter water monitoring policies have been mandated in the
        state in an attempt to control the human and environmental harm caused
        by pollutants.
      </p>
      <p>
        Section 303(d) of the Clean Water Act (CWA) establishes that states are
        to list (the 303(d) list) waters for which technology-based limits alone
        do not ensure attainment of applicable water quality standards.
        <br /><br /><br />
        The Alabama Department of Environmental Management (ADEM) creates these
        lists which can be found here:
        <a href="http://adem.alabama.gov/programs/water/303d.cnt"
          >ADEM 303(d)</a
        >
        <br /><br />
        The past 20 years of impaired 303(d) waters are aggregated and organized
        by the major river basin. Data is used to visualize the scope of water
        contamination by size, cause, and source.This project seeks to analyze
        the progress that has been made during the past 20 years of water
        quality testing.
      </p>
    </div>
    <!--  -->
    <div class="curved-div">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#fff"
          fill-opacity="1"
          d="M0,96L80,80C160,64,320,32,480,48C640,64,800,128,960,133.3C1120,139,1280,85,1360,58.7L1440,32L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"
        ></path>
      </svg>
      <div class="spacer"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MapBasinSection",
};
</script>

<style scoped>
.map2 {
  display: grid;
  position: relative;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  margin-top: 10%;
  background-image: linear-gradient(
      to left,
      rgb(116, 156, 243, 0.4),
      rgb(158, 188, 216, 0.7)
    ),
    linear-gradient(rgb(158, 188, 216, 0.1), rgba(0, 104, 40, 1));
  background-repeat: no-repeat;
  background-size: 100% 100%;
  width: 100%;
  height: 100vh;
  grid-template-columns: minmax(5px, 40px) minmax(5px, 50px) auto minmax(5px, 50px) minmax(5px, 40px);
  grid-template-rows: 25% 100px 100px 100px auto;
}
.map2 img {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 2;
  grid-row-end: span 2;
  margin-left: -2%;
  border-radius: 20px;
}
.map2 h1 {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: span 2;
  z-index: 1;
  font-size: clamp(2em, 5vw, 3em);
  margin-left: 10%;
  margin-top: 17%;
}
@media (min-width: 1024px) {
  .map2 h1 {
    margin-left: 35%;
  }
}
.map2 .transbox2 {
  margin-left: 5%;
  margin-right: 5%;
  grid-column-start: 3;
  grid-column-end: 3;
  grid-row-start: 3;
  grid-row-end: 5;
  border-radius: 55px;
  opacity: 1;
  margin-bottom: 7%;
  margin-top: 7%;
  text-align: left;
}
@media (min-width: 1024px) {
  .map2 .transbox2 {
    margin-left: 37%;
    margin-right: 0;
  }
}
.map2 .transbox2 p {
  margin-bottom: 4%;
  text-align: left;
  font-size: 1.3em;
  opacity: 1;
  font-weight: bold;
}
.map2 .curved-div {
  grid-column-start: 1;
  grid-column-end: 6;
  grid-row-start: 1;
  grid-row-end: 1;
  margin-top: -6.1%;
}
.map2 .curved-div svg {
  width: 100%;
  height: auto;
  text-align: top;
  margin-top: 6%;
}
.curved-div {
  position: block;
  height: 55vh;
  width: 100%;
}
.spacer {
  display: block;
  height: 2vh;
  width: 100%;
}
</style>
