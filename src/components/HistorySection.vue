<template>
  <div class="IntroGlacier3" style="height: 90vh">
    <h2>A Troubling History</h2>
    <h3>
      A history of industrial accidents, oversight, and abuse has led to
      disasters that have harmed everything from ponds to rivers and cities.
    </h3>
    <!--  -->
    <div class="drop">
      <p class="droptxt">Monsanto PCB plant in Anniston</p>
      <svg
        width="100%"
        height="100%"
        viewBox="0 0 32 32"
        @mouseenter="dropHover = true"
        @mouseleave="dropHover = null"
      >
        <defs>
          <linearGradient id="linear1" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
            <pattern
              id="img1"
              patternUnits="userSpaceOnUse"
              width="58"
              height="70"
            >
              <image
                href="../assets/monsantoAnniston.jpg"
                x="-4.5"
                y="-14"
                width="58"
                height="70"
              />
            </pattern>
          </linearGradient>
        </defs>
        <path
          fill="url(#img1)"
          opacity="1"
          stroke="url(#linear1)"
          stroke-width=".2"
          d="M15
        3 Q16.5 6.8 25 18 A12.8 12.8 0 1 1 5 18 Q13.5 6.8 15 3z"
        />
      </svg>
    </div>
    <!--  -->
    <div class="drop2">
      <p class="droptxt">Coal Ash Waste at Barry Power Plant</p>
      <svg width="100%" height="100%" viewBox="0 0 32 32">
        <defs>
          <linearGradient id="linear2" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
          </linearGradient>
          <pattern
            id="img2"
            patternUnits="userSpaceOnUse"
            width="100"
            height="55"
          >
            <image
              href="../assets/BarryAsh.jpg"
              x="-45"
              y="0"
              width="100"
              height="55"
            />
          </pattern>
        </defs>
        <path
          fill="url(#img2)"
          opacity="1"
          stroke="url(#linear2)"
          stroke-width=".2"
          d="M15 3
           Q16.5 6.8 25 18
           A12.8 12.8 0 1 1 5 18
           Q13.5 6.8 15 3z"
        />
      </svg>
    </div>
    <!--  -->
    <div class="drop3">
      <p class="droptxt">Lay Dam Coosa River</p>
      <svg width="100%" height="100%" viewBox="0 0 32 32">
        <defs>
          <linearGradient id="linear3" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
          </linearGradient>
          <pattern
            id="img3"
            patternUnits="userSpaceOnUse"
            width="45"
            height="65"
          >
            <image
              href="../assets/LayDamCoosa.jpg"
              x="-4"
              y="-11"
              width="45"
              height="65"
            />
          </pattern>
        </defs>
        <path
          fill="url(#img3)"
          opacity="1"
          stroke="url(#linear3)"
          stroke-width=".2"
          d="M15 3
           Q16.5 6.8 25 18
           A12.8 12.8 0 1 1 5 18
           Q13.5 6.8 15 3z"
        />
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  name: "HistorySection",
  data() {
    return {
      dropHover: null,
    };
  },
};
</script>

<style scoped>
.IntroGlacier3 {
  display: grid;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px 100px 100px auto;
  margin-top: 15%;
}
.IntroGlacier3 > h2 {
  margin-left: 44%;
  margin-right: 10%;
  font-size: clamp(2em, 5vw, 3em);
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 2;
  color: black;
}
.IntroGlacier3 > h3 {
  text-align: left;
  grid-column-start: 3;
  grid-column-end: 5;
  grid-row-start: 2;
  grid-row-end: 5;
  margin-left: 55%;
  margin-right: 10%;
  margin-top: -2%;
}
.drop {
  margin-top: -15px;
  grid-column-start: 3;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 6;
}
.IntroGlacier3 .drop {
  margin-left: 25%;
  margin-right: 25%;
  margin-bottom: -5%;
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 6;
  transform: scale(0.9, 0.9);
}
.IntroGlacier3 .drop2 {
  margin-left: 74%;
  margin-right: 0%;
  margin-bottom: 4%;

  margin-top: 18%;
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 6;
}
.IntroGlacier3 .drop3 {
  grid-column-start: 2;
  grid-column-end: span 3; /* Fixed typo from span3 */
  grid-row-start: 1;
  grid-row-end: 6;
}
.drop .droptxt:hover,
.drop2 .droptxt:hover,
.drop3 .droptxt:hover {
  opacity: 1;
  color: red;
}
.drop .droptxt {
  position: absolute;
  margin-left: 65%;
  margin-top: 35%;
  opacity: 0.1;
  height: 50px;
  transition: opacity 0.3s, color 0.3s;
}

.drop2 .droptxt {
  position: absolute;
  margin-left: -9%;
  margin-top: 23%;
  opacity: 0.1;
  transition: opacity 0.3s, color 0.3s;
}

.drop3 .droptxt {
  position: absolute;
  margin-left: 13%;
  margin-top: 3%;
  opacity: 0.11;
  transition: opacity 0.3s, color 0.3s;
}
</style>
