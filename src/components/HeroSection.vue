<template>
  <div class="HeroSection">
    <div class="hero-content content-container">
      <span class="main-title">20 Years of Water</span>
      <p class="sub-title">Visualising Alabama's List of Impaired Waters</p>
    </div>
    <div class="wave-transition">
      <svg viewBox="0 0 1440 320" preserveAspectRatio="none">
        <path
          fill="white"
          fill-opacity="1"
          d="M0,32L48,80C96,128,192,224,288,224C384,224,480,128,576,90.7C672,53,768,75,864,96C960,117,1056,139,1152,149.3C1248,160,1344,160,1392,160L1440,160L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
        ></path>
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeroSection",
};
</script>

<style scoped>
.HeroSection {
  position: relative;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  background-color: var(--bg-color);
  overflow: hidden;
}
.hero-content {
  text-align: center;
  z-index: 2;
  margin-top: -10vh;
}
.main-title {
  display: block;
  font-family: var(--serif-font);
  font-size: clamp(3rem, 10vw, 8rem);
  font-weight: 800;
  color: #333;
  line-height: 1;
  margin-bottom: 20px;
}
.sub-title {
  font-family: var(--sans-font);
  font-size: clamp(1rem, 2.5vw, 2rem);
  color: #666;
  max-width: 600px;
  margin: 0 auto;
}
.wave-transition {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 20vh;
  z-index: 1;
}
.wave-transition svg {
  width: 100%;
  height: 100%;
}
</style>
