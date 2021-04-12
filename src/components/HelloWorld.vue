<template>
  <div class="hello">
    <div
      class="background_image"
      :style="{ color: 'red', fontSize: 25 + 'px', height: '300px' }"
    >
      <div class="transbox">
        <p>This is some text that is placed in the transparent box.</p>
      </div>
      <!-- <div class="text"><p>TESTING55555</p></div> -->
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
div.transbox {
  margin-left: 0%;
  margin-right: 0%;
  width: 600px;
  background-color: #ffffff;
  border: 1px solid black;
  opacity: 0.6;
  background-position: 50% 0;
}

div.transbox p {
  margin: 5%;
  font-weight: bold;
  color: #000000;
}
.background_image {
  background-image: url("https://cdn.britannica.com/s:400x225,c:crop/97/158797-050-ABECB32F/North-Cascades-National-Park-Lake-Ann-park.jpg");
  background-size: contain;
  background-repeat: no-repeat;
  background-position: 50% 0;
  /* opacity: 0.5; */
}
</style>
