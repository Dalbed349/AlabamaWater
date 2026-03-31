<template>
  <div class="map">
    <div class="curved-div">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#fff"
          fill-opacity="1"
          d="M0,96L80,80C160,64,320,32,480,48C640,64,800,128,960,133.3C1120,139,1280,85,1360,58.7L1440,32L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"
        ></path>
      </svg>
    </div>
    <h1>What is being done?</h1>
    <img src="../assets/keepers.svg" />

    <div class="transbox">
      <h2>The Riverkeepers</h2>
      <p>
        Various organizations help study and protect the water basins listed in
        this dataset.
        <br /><br />They act independently, but help inform decisions, from
        state agencies such as Alabama Department of Environmental Protection.
        <br />Current news and research regarding each basin linked below or
        visit: <a href="http://waterkeepersalabama.org/" target="_blank">http://waterkeepersalabama.org/</a>
        <br />
        <br />
      </p>
      <p id="resourcelinks">
        <a href="https://www.mobilebaykeeper.org/" target="_blank">https://www.mobilebaykeeper.org/</a><br />
        <a href="https://blackwarriorriver.org/" target="_blank">https://blackwarriorriver.org/</a><br />
        <a href="https://www.tennesseeriverkeeper.org/" target="_blank">https://www.tennesseeriverkeeper.org/</a><br />
        <a href="https://littleriverwaterkeeper.org/" target="_blank">https://littleriverwaterkeeper.org/</a><br />
        <a href="https://coosa.org/" target="_blank">https://coosa.org/</a><br />
        <a href="https://chattahoochee.org/" target="_blank">https://chattahoochee.org/</a><br />
        <a href="https://cahabariverkeeper.org/" target="_blank">https://cahabariverkeeper.org/</a><br />
        <a href="https://www.choctawhatcheeriver.org/" target="_blank">https://www.choctawhatcheeriver.org/</a><br />
        <a href="http://www.hurricanecreek.org/" target="_blank">http://www.hurricanecreek.org/</a><br />
      </p>
    </div>
    <div class="transbox2">
      <p>
        This project was prepared as part of the Parson's Data Visualization
        (M.S.) Program. <br /><br />
        Files and documentation can be found at
        <a href="https://github.com/Dalbed349/AlabamaWater/"
          >github.com/Dalbed349/AlabamaWater/</a
        >
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "FooterSection",
};
</script>

<style scoped>
.map {
  display: grid;
  position: relative;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(
      to right,
      rgba(255, 255, 255, 0),
      rgba(59, 45, 4, 0.198)
    ),
    linear-gradient(to left, rgba(255, 255, 255, 0), rgba(23, 99, 143, 0.616)),
    url("../assets/cahaba.jpg");
  background-repeat: no-repeat;
  width: 100%;
  height: 100vh;
  opacity: 1;
  margin-top: 7%;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px 100px 100px auto;
  margin-bottom: -1%;
  background-size: 100% 100%;
}
.map .curved-div {
  margin-top: -3%;
  position: relative;
  grid-column-start: 1;
  grid-column-end: 6;
  grid-row-start: 1;
  grid-row-end: 1;
}
.curved-div {
  position: block;
  height: 55vh;
  width: 100%;
}
.curved-div svg {
  width: 100%;
  height: auto;
  text-align: top;
  margin-top: 2%;
}
.map h1 {
  margin-right: 0%;
  margin-top: 1%;
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: span 2;
  font-size: 3em;
  z-index: 1;
  color: #000;
  margin-left: 45%;
  margin-top: 3%;
}
.map img {
  transform: scale(9, 9);
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 2;
  border-radius: 20px;
  margin-top: -5%;
  height: 100%;
  margin-left: 35%;
  margin-top: 13%;
}
.map .transbox {
  margin-left: 55%;
  margin-right: 5%;
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: span 2;
  font-size: 1em;
  color: #000000;
  margin-bottom: -20.5%;
  margin-top: 1%;
  border-radius: 50px;
  background-color: #ffffff;
  border: none;
  font-weight: bold;
}
.map .transbox h2 {
  margin-top: 2%;
  margin-bottom: -2%;
  margin-left: 5%;
  margin-right: 5%;
}
.map .transbox p {
  margin-top: 5%;
  font-size: 1.1em;
  margin-left: 5%;
  margin-right: 5%;
}
.map .transbox2 {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 5;
  grid-row-end: 6;
  border-radius: 55px;
  background-color: #ffffff;
  opacity: 1; /* Removed duplicate 0.9 */
  margin-bottom: 10%;
  margin-top: 17%;
  margin-left: 53%;
  margin-right: 5%;
}
.map .transbox2 p {
  margin-top: 2%;
  font-size: 1em;
}
#resourcelinks {
  font-size: 0.9em;
  margin-top: 0%;
}
</style>
