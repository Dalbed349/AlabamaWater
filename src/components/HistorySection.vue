<template>
  <section class="HistorySection">
    <div class="content-container section-header">
      <h2>A Troubling History</h2>
      <p class="section-intro">
        A history of industrial accidents, oversight, and abuse has led to
        disasters that have harmed everything from ponds to rivers and cities.
      </p>
    </div>

    <div class="case-studies-grid content-container">

      <!-- Lay Dam Coosa River -->
      <div class="case-study">
        <div class="drop-large">
          <svg viewBox="0 0 32 32">
            <defs>
              <pattern id="imgLayDam" patternUnits="userSpaceOnUse" width="32" height="32">
                <image href="../assets/LayDamCoosa.jpg" x="0" y="0" width="32" height="32" preserveAspectRatio="xMidYMid slice" />
              </pattern>
            </defs>
            <path fill="url(#imgLayDam)" d="M15 3 Q16.5 6.8 25 18 A12.8 12.8 0 1 1 5 18 Q13.5 6.8 15 3z" />
          </svg>
        </div>
        <p class="case-label">Lay Dam <br> Coosa River</p>
      </div>

      <!-- Monsanto PCB plant in Anniston -->
      <div class="case-study">
        <div class="drop-large">
          <svg viewBox="0 0 32 32">
            <defs>
              <pattern id="imgMonsanto" patternUnits="userSpaceOnUse" width="32" height="32">
                <image href="../assets/monsantoAnniston.jpg" x="0" y="0" width="32" height="32" preserveAspectRatio="xMidYMid slice" />
              </pattern>
            </defs>
            <path fill="url(#imgMonsanto)" d="M15 3 Q16.5 6.8 25 18 A12.8 12.8 0 1 1 5 18 Q13.5 6.8 15 3z" />
          </svg>
        </div>
        <p class="case-label">Monsanto PCB plant <br> in Anniston</p>
      </div>

      <!-- Coal Ash Waste at Barry Power Plant -->
      <div class="case-study">
        <div class="drop-large">
          <svg viewBox="0 0 32 32">
            <defs>
              <pattern id="imgCoalAsh" patternUnits="userSpaceOnUse" width="32" height="32">
                <image href="../assets/BarryAsh.jpg" x="0" y="0" width="32" height="32" preserveAspectRatio="xMidYMid slice" />
              </pattern>
            </defs>
            <path fill="url(#imgCoalAsh)" d="M15 3 Q16.5 6.8 25 18 A12.8 12.8 0 1 1 5 18 Q13.5 6.8 15 3z" />
          </svg>
        </div>
        <p class="case-label">Coal Ash Waste <br> Barry Power Plant</p>
      </div>
    </div>
  </section>
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
.HistorySection {
  background-color: #f0f4f5;
  padding: 120px 0;
}
.section-header {
  margin-bottom: 80px;
}
h2 {
  font-size: 3.5rem;
  margin-bottom: 20px;
}
.section-intro {
  font-size: 1.4rem;
  color: #444;
  max-width: 700px;
}
.case-studies-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 40px;
  max-width: 1000px !important;
}
.case-study {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}
.drop-large {
  width: 100%;
  aspect-ratio: 1;
  max-width: 280px;
  filter: drop-shadow(0 10px 20px rgba(0,0,0,0.1));
  transition: transform 0.3s ease;
}
.drop-large:hover {
  transform: translateY(-5px);
}
.case-label {
  margin-top: 25px;
  font-weight: 700;
  font-size: 1.1rem;
  color: #1a1a1a;
  line-height: 1.4;
}
@media (max-width: 768px) {
  .case-studies-grid {
    grid-template-columns: 1fr;
  }
}
</style>
