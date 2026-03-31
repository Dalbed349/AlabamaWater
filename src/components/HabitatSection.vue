<template>
  <div class="map3">
    <div class="curved-div">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#fff"
          fill-opacity="1"
          d="M0,64L60,64C120,64,240,64,360,53.3C480,43,600,21,720,53.3C840,85,960,171,1080,202.7C1200,235,1320,213,1380,202.7L1440,192L1440,0L1380,0C1320,0,1200,0,1080,0C960,0,840,0,720,0C600,0,480,0,360,0C240,0,120,0,60,0L0,0Z"
        ></path>
      </svg>
    </div>
    <h1>A Lush Habitat</h1>
    <div class="drop">
      <svg width="100%" height="101%" viewBox="0 0 32 32">
        <defs>
          <linearGradient id="linearHabitat" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
          </linearGradient>
        </defs>
        <path
          fill="white"
          opacity="1"
          stroke-width=".2"
          d="M15 3 Q16.5 6.8 25 18 A12.8 12.8 0 1 1 5 18 Q13.5 6.8 15 3z"
        />
      </svg>
    </div>
    <div class="transbox3">
      <p id="bigger1">
        <br />
        Alabama's climate and geographic history make it one of the most
        ecologically diverse states in the U.S. <br />
      </p>
      <p id="bigger">
        During the Ice Age much of this land remained unfrozen due to its
        lattitude. A combination of proximity to coastal waters and geological
        formations around inland waters allowed for evolution to continue
        unabated while most of the planet was covered in ice.
      </p>

      <p id="bigger">
        Today the state ranks number one in the country for aquatic biodiversity
        with more than 450 known species of freshwater fish.<br /><br />
      </p>

      <p></p>
    </div>

    <div class="transbox2">
      <p>
        Black Warrior River <br />
        Photo by Riverkeeper Nelson Brooke
        <a href="https://www.w3schools.com/">Nelson Brooke</a>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HabitatSection",
};
</script>

<style scoped>
.map3 {
  margin-top: -1%;
  display: grid;
  position: relative;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0%;
  right: 0%;
  background-image: linear-gradient(
      rgba(69, 143, 161, 0.075),
      rgba(0, 0, 0, 0.4)
    ),
    url("../assets/Blackwarrior.jpg");
  background-repeat: no-repeat;
  background-size: 100% 100%;
  width: 100%;

  margin-bottom: 2%;
  height: 100vh;
  opacity: 1;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 10% auto 100px auto;
}
.map3 .curved-div {
  grid-column-start: 1;
  grid-column-end: 6;
  grid-row-start: 1;
  grid-row-end: 1;
  margin-top: -8%;
  transform: scale(1, 0.6);
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
.map3 > h1 {
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 2;
  font-size: 3em;
  margin-left: 75%;
  z-index: 1;
  color: #000;
}
.drop {
  margin-top: -15px;
  margin-left: 0%;
  grid-column-start: 3;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 6;
}
.map3 .drop {
  margin-top: 10%;
}
div.transbox3 p {
  font-weight: bold;
  font-size: 18px;
  color: rgb(0, 0, 0);
}

div.transbox3 {
  position: absolute;
  margin-left: 12%;
  margin-top: 4%;
  text-align: left;
  margin-right: 68%;
  grid-column-start: 3;
  grid-column-end: 3;
  grid-row-start: 2;
  grid-row-end: 4;
  border-radius: 55px;
}
.map3 .transbox3 {
  margin-top: 15%;
  margin-left: 11%;
  margin-right: 74%;
}
.map3 #bigger {
  margin-left: -25%;
  margin-right: -45%;
  margin-bottom: 5%;
  margin-top: 5%;
}
.map3 #bigger1 {
  margin-left: -5%;
  margin-right: -20%;
  margin-bottom: 10%;
  margin-top: 5%;
  font-size: 1.5em;
}
.map3 .transbox2 {
  margin-left: 85%;
  margin-right: 0%;
  margin-top: 25%;
  margin-bottom: 0%;
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 5;
  grid-row-end: 5;
  opacity: 1;
}
.map3 .transbox2 p {
  font-weight: bold;
  font-size: 12px;
  color: #ffffff;
  margin: 20px;
  opacity: 0.7;
}
</style>
