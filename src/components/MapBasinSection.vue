<template>
  <section class="MethodologySection">
    <div class="content-container">
      <h2>Data & Methodology</h2>
      <p class="intro-text">
        Since 1998, stricter water monitoring policies have been mandated in the
        state in an attempt to control the human and environmental harm caused
        by pollutants.
      </p>

      <div class="methodology-grid">
        <div class="methodology-text">
          <p>
            Section 303(d) of the Clean Water Act (CWA) establishes that states are
            to list waters for which technology-based limits alone do not ensure 
            attainment of applicable water quality standards.
          </p>
          <p>
            The Alabama Department of Environmental Management (ADEM) creates these
            lists which can be found at the 
            <a href="http://adem.alabama.gov/programs/water/303d.cnt" target="_blank">ADEM 303(d) Portal</a>.
          </p>
          <p class="highlight-box">
            The past 20 years of impaired 303(d) waters are aggregated and organized
            by the major river basin. This project seeks to analyze
            the progress that has been made during these two decades of water
            quality testing.
          </p>
        </div>
        
        <div class="methodology-image">
          <img alt="River Basins of Alabama" src="../assets/riverBasins.png" />
          <p class="caption">The River Basins of Alabama</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "MapBasinSection",
};
</script>

<style scoped>
.MethodologySection {
  padding: 100px 0;
  background-color: #fff;
}
h2 {
  font-size: 3rem;
  margin-bottom: 40px;
}
.intro-text {
  font-size: 1.4rem;
  color: #444;
  margin-bottom: 60px;
  max-width: 700px;
}
.methodology-grid {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 60px;
  align-items: start;
}
.methodology-text p {
  margin-bottom: 25px;
  font-size: 1.15rem;
  line-height: 1.7;
}
.highlight-box {
  background-color: #f0f7f8;
  padding: 30px;
  border-radius: 8px;
  border-left: 4px solid teal;
  font-weight: 500;
  color: #0d4d4d;
}
.methodology-image {
  text-align: center;
}
.methodology-image img {
  width: 100%;
  max-width: 400px;
  border-radius: 12px;
}
.caption {
  font-size: 0.9rem;
  color: #666;
  margin-top: 15px;
  font-style: italic;
}
@media (max-width: 900px) {
  .methodology-grid {
    grid-template-columns: 1fr;
  }
  .methodology-image {
    order: -1;
    margin-bottom: 40px;
  }
}
</style>
