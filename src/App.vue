<template>
  <div id="app">
    <div id="nav">
      <router-link to="/" class="router">Inicio</router-link> |
      <router-link to="/meteo" class="router">Meteosat</router-link>
    </div>
    <router-view/>
  </div>
</template>




  <script>
  // @ is an alias to /src

  export default {
    name: 'app',
    components: {
    }
  }
  </script>
<style>
  #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
  padding-left: 50px;
  background-color: #222222;
  padding-right: 50px ;
}
  #nav {
    padding-bottom: 20px;
    padding-left: 45%;

  }
  .router{
    color: white;
  }
</style>
