<template>
  <section class="HabitatSection">
    <div class="content-container">
      <h2>A Lush Habitat</h2>
      <div class="article-text">
        <p class="lead">
          Alabama's climate and geographic history make it one of the most
          ecologically diverse states in the U.S.
        </p>
        <p>
          During the Ice Age, much of this land remained unfrozen due to its
          latitude. A combination of proximity to coastal waters and geological
          formations around inland waters allowed for evolution to continue
          unabated while most of the planet was covered in ice.
        </p>
        <p>
          Today, the state ranks number one in the country for aquatic biodiversity
          with more than 450 known species of freshwater fish.
        </p>
      </div>
      
      <div class="photo-credit">
        <p>
          Black Warrior River <br />
          Photo by Riverkeeper <a href="https://blackwarriorriver.org/">Nelson Brooke</a>
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "HabitatSection",
};
</script>

<style scoped>
.HabitatSection {
  background-color: white;
  padding: 100px 0;
}
h2 {
  font-size: 3.5rem;
  margin-bottom: 40px;
  color: #111;
}
.article-text {
  max-width: 100%;
}
.lead {
  font-size: 1.5rem;
  font-weight: 500;
  margin-bottom: 30px;
  color: #333;
}
.photo-credit {
  margin-top: 60px;
  border-top: 1px solid #eee;
  padding-top: 20px;
}
.photo-credit p {
  font-size: 0.9rem;
  color: #888;
  font-style: italic;
}
.photo-credit a {
  color: #5696bc;
  text-decoration: none;
}
</style>
