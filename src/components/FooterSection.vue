<template>
  <footer class="FooterSection">
    <div class="content-container">
      <h2>The Riverkeepers</h2>
      <p class="footer-intro">
        Various organizations help study and protect the water basins listed in
        this dataset. They act independently but inform decisions by state 
        agencies such as the Alabama Department of Environmental Management (ADEM).
      </p>

      <div class="resource-grid">
        <div class="riverkeepers-list">
          <h3>Local Organizations</h3>
          <p id="resourcelinks">
            <a href="https://www.mobilebaykeeper.org/" target="_blank">Mobile Baykeeper</a><br />
            <a href="https://blackwarriorriver.org/" target="_blank">Black Warrior Riverkeeper</a><br />
            <a href="https://www.tennesseeriverkeeper.org/" target="_blank">Tennessee Riverkeeper</a><br />
            <a href="https://littleriverwaterkeeper.org/" target="_blank">Little River Waterkeeper</a><br />
            <a href="https://coosa.org/" target="_blank">Coosa Riverkeeper</a><br />
            <a href="https://chattahoochee.org/" target="_blank">Chattahoochee Riverkeeper</a><br />
            <a href="https://cahabariverkeeper.org/" target="_blank">Cahaba Riverkeeper</a><br />
            <a href="https://www.choctawhatcheeriver.org/" target="_blank">Choctawhatchee Riverkeeper</a><br />
            <a href="http://www.hurricanecreek.org/" target="_blank">Friends of Hurricane Creek</a>
          </p>
          <p class="central-link">
            Visit: <a href="http://waterkeepersalabama.org/" target="_blank">Waterkeepers Alabama</a>
          </p>
        </div>

        <div class="project-info">
          <h3>About the Project</h3>
          <p>
            This project was prepared as part of the Parsons Data Visualization
            (M.S.) Program.
          </p>
          <p>
            Explore the source code and documentation at: <br>
            <a href="https://github.com/Dalbed349/AlabamaWater/" target="_blank">
              github.com/Dalbed349/AlabamaWater/
            </a>
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterSection",
};
</script>

<style scoped>
.FooterSection {
  padding: 100px 0;
  background-color: #1a1a1a;
  color: #fff;
}
h2 {
  font-size: 3rem;
  margin-bottom: 20px;
}
.footer-intro {
  font-size: 1.2rem;
  color: #ccc;
  margin-bottom: 60px;
  max-width: 600px;
}
.resource-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  text-align: left;
}
h3 {
  font-size: 1.5rem;
  margin-bottom: 25px;
  color: teal;
}
#resourcelinks a {
  color: #fff;
  text-decoration: none;
  font-size: 1.1rem;
  line-height: 2;
  transition: color 0.2s;
}
#resourcelinks a:hover {
  color: teal;
}
.central-link {
  margin-top: 30px;
  padding-top: 20px;
  border-top: 1px solid #333;
}
.central-link a {
  color: teal;
  font-weight: bold;
}
.project-info p {
  color: #aaa;
  margin-bottom: 20px;
}
.project-info a {
  color: teal;
}
@media (max-width: 768px) {
  .resource-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }
}
</style>
