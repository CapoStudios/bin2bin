<template>
  <div class="container">
     <Converter />
  </div>
</template>

<script>
import Converter from './components/Converter.vue'

export default {
  name: 'App',
  components: {
    Converter,
    
  },
  created(){
    console.warn("Created by CapoStudios");
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

::selection {
    background-color: #22b455;
    color: #000;
}

canvas {
  display: block;
  position: absolute;
  z-index: -999;
}

body {
  font-family: 'Poppins';
  background-color: #000;
  overflow: hidden;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #1C1C1C;
  background-color: rgba(0,0,0, 0);
  margin-top: 60px;
  overflow: hidden;
}

.container {
  width: 400px;
  height: 400px;
  margin: 0 auto;
  overflow: auto;
  border: 2px solid #1C1C1C;
  background-color: #eee;
  padding: 30px;
  border-radius: 25px;
}

@media only screen and (max-width: 600px) {
  #app {
    margin-top: 40px;
    padding-right: 0;
  }
  .container {
    height: 340px;
    width: 350px;
    overflow: hidden;
  }
}
</style>
