<template>
  <div class="container">
    <h1 id="titlePart1">
      tk<span id="titlePart2">ambio</span>
    </h1>
  </div>
</template>

<script>
export default {
  name: 'NavBar'
};
</script>

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
.container {
  padding: 0.05rem;
  background: linear-gradient(180deg, #02ADF1 0%, #4562E6 50%, #4563E6 100%);
  box-shadow: 0px 5px 5px grey;
}
h1 {
  font-size: 2.5rem;
  letter-spacing: 0.06em;
}
#titlePart1 {
  color: #FFBE12;
  font-weight: 1000;
}
#titlePart2 {
  color: white;
}
</style>
