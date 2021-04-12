<template>
  <div class="hello">
  <div :style="{height:'500px', width:'500px'}">    </div>
       <div class="background_image" :style="{ color: 'red', fontSize: 25 + 'px',height: '300px'  }"></div>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
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
.background_image {
 background-image:url("https://cdn.britannica.com/s:400x225,c:crop/97/158797-050-ABECB32F/North-Cascades-National-Park-Lake-Ann-park.jpg");
background-size: cover;
}

</style>
