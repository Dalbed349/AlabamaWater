<template>
  <div class="HistorySection">
    <div class="header-block">
      <h2>A Troubling History</h2>
      <h3>
        A history of industrial accidents, oversight, and abuse has led to
        disasters that have harmed everything from ponds to rivers and cities.
      </h3>
    </div>

    <!-- Lay Dam Coosa River -->
    <div class="drop-container lay-dam">
      <svg
        width="100%"
        height="100%"
        viewBox="0 0 32 32"
      >
        <defs>
          <linearGradient id="linearLayDam" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
          </linearGradient>
          <pattern
            id="imgLayDam"
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
          fill="url(#imgLayDam)"
          stroke="url(#linearLayDam)"
          stroke-width="0.3"
          d="M15 3 Q16.5 6.8 25 18 A12.8 12.8 0 1 1 5 18 Q13.5 6.8 15 3z"
        />
      </svg>
      <p class="drop-label">Lay Dam Coosa River</p>
    </div>

    <!-- Monsanto PCB plant in Anniston -->
    <div class="drop-container monsanto">
      <svg
        width="100%"
        height="100%"
        viewBox="0 0 32 32"
      >
        <defs>
          <linearGradient id="linearMonsanto" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
            <pattern
              id="imgMonsanto"
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
          fill="url(#imgMonsanto)"
          stroke="url(#linearMonsanto)"
          stroke-width="0.4"
          d="M15 3 Q16.5 6.8 25 18 A12.8 12.8 0 1 1 5 18 Q13.5 6.8 15 3z"
        />
      </svg>
      <p class="drop-label">Monsanto PCB plant in Anniston</p>
    </div>

    <!-- Coal Ash Waste at Barry Power Plant -->
    <div class="drop-container coal-ash">
      <svg width="100%" height="100%" viewBox="0 0 32 32">
        <defs>
          <linearGradient id="linearCoalAsh" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="10%" stop-color="#fff" />
            <stop offset="100%" stop-color="teal" />
          </linearGradient>
          <pattern
            id="imgCoalAsh"
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
          fill="url(#imgCoalAsh)"
          stroke="url(#linearCoalAsh)"
          stroke-width="0.3"
          d="M15 3 Q16.5 6.8 25 18 A12.8 12.8 0 1 1 5 18 Q13.5 6.8 15 3z"
        />
      </svg>
      <p class="drop-label">Coal Ash Waste at Barry Power Plant</p>
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
.HistorySection {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  grid-auto-rows: minmax(100px, auto);
  gap: 20px;
  padding: 5% 5% 5% 5%;
  min-height: auto;
  max-width: 1400px;
  margin: 0 auto;
  align-items: center;
}

.header-block {
  grid-column: 3 / 6;
  grid-row: 1;
  text-align: left;
  padding-left: 20px;
}

.header-block h2 {
  font-size: clamp(2.5em, 5vw, 4em);
  color: #000;
  margin-bottom: 20px;
  font-weight: bold;
}

.header-block h3 {
  font-size: clamp(1.1em, 2vw, 1.5em);
  color: #333;
  font-weight: normal;
  line-height: 1.5;
  max-width: 600px;
}

.drop-container {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}

.drop-label {
  position: absolute;
  color: #444;
  font-size: 1.1em;
  opacity: 0.8;
  transition: opacity 0.3s, color 0.3s;
  pointer-events: none;
  white-space: nowrap;
}

.drop-container:hover .drop-label {
  opacity: 1;
  color: #d84541;
  font-weight: bold;
}

/* Specific Placements matching 1.png */
.lay-dam {
  grid-column: 1 / 3;
  grid-row: 1 / 3;
  width: 90%;
  justify-self: start;
}
.lay-dam .drop-label {
  top: 15%;
  left: 80%;
}

.monsanto {
  grid-column: 2 / 4;
  grid-row: 2 / 5;
  width: 130%; /* Massive Drop */
  margin-left: -15%;
  z-index: 2;
}
.monsanto .drop-label {
  top: 50%;
  right: 80%;
  margin-right: 10px;
}

.coal-ash {
  grid-column: 4 / 6;
  grid-row: 3 / 5;
  width: 100%;
  margin-top: 10%;
  justify-self: center;
}
.coal-ash .drop-label {
  bottom: 10%;
  right: 75%;
}

@media (max-width: 1024px) {
  .HistorySection {
    grid-template-columns: 1fr 1fr;
  }
  .header-block {
    grid-column: 1 / 3;
    grid-row: 1;
  }
  .lay-dam {
    grid-column: 1;
    grid-row: 2;
    width: 100%;
  }
  .monsanto {
    grid-column: 1 / 3;
    grid-row: 3;
    width: 80%;
    margin-left: 0;
    justify-self: center;
  }
  .coal-ash {
    grid-column: 2;
    grid-row: 4;
    width: 100%;
    margin-top: 0;
  }
}
@media (max-width: 768px) {
  .HistorySection {
    grid-template-columns: 1fr;
  }
  .header-block {
    grid-column: 1;
  }
  .lay-dam, .monsanto, .coal-ash {
    grid-column: 1;
    grid-row: auto;
    width: 100%;
    justify-self: center;
  }
}
</style>
