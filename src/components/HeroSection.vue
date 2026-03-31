<template>
  <div class="IntroGlacier">
    <div class="darken"></div>
    <div class="margins"></div>
    <div class="curved-div">
      <span style="color: #333">20 Years of </span>

      <span style="color: #333">Water</span>
      <p style="color: #555">Visualising Alabama's List of Impaired Waters</p>
      <svg viewBox="0 0 1440 319">
        <path
          fill="#f8fcfd"
          fill-opacity="1"
          d="M0,32L48,80C96,128,192,224,288,224C384,224,480,128,576,90.7C672,53,768,75,864,96C960,117,1056,139,1152,149.3C1248,160,1344,160,1392,160L1440,160L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
        ></path>
      </svg>
      <div class="spacer"></div>
    </div>
  </div>
  <!-- . -->
  <div class="IntroGlacier2"></div>
</template>

<script>
export default {
  name: "HeroSection",
};
</script>

<style scoped>
.IntroGlacier {
  position: relative;
  height: 100vh;
}
.IntroGlacier2 {
  display: grid;
  grid-template-columns: minmax(10px, 40px) minmax(10px, 50px) auto minmax(10px, 50px) minmax(10px, 40px);
  grid-template-rows: 25%;
  margin-top: 15%;
}
.IntroGlacier .darken {
  position: absolute;
  z-index: -1;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: #f8fcfd;
  width: 100%;
  height: 100%;
}
.margins {
  margin-top: 35vh;
}
.curved-div {
  position: block;
  height: 55vh;
  width: 100%;
}
.curved-div span {
  font-size: clamp(3rem, 8vw, 8rem);
  font-weight: bold;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: black;
}
.curved-div p {
  font-size: clamp(1rem, 3vw, 2rem);
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
.curved-div svg {
  width: 100%;
  height: auto;
  text-align: top;
  margin-top: 2%;
}
.spacer {
  display: block;
  height: 2vh;
  width: 100%;
}
</style>
