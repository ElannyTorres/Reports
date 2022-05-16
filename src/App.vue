<template>

  <NavBar></NavBar>

  <HelloWorld msg="Generador de reportes TK"/>

</template>

<script>

  import HelloWorld from './components/HelloWorld.vue'
  import NavBar from './components/Navbar.vue'

  /* const routes = {
    '/': HelloWorld,
    '/reports': NavBar
  } */

  export default {
    name: 'App',
    components: {
      NavBar,
      HelloWorld
    }
  }

</script>

<style>
  html, body {
    margin: 0;
    padding: 0;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

</style>
