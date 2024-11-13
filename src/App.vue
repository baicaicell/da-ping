<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>

import Home from './views/home/index.vue'
export default {
  name: 'App',
  components: {
    Home
  }
}

</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;

}

body,
html {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

#app {
  width: 100%;
  height: 100%;
  background: url(./assets/bg.png) no-repeat;
  background-size: cover;
  background-color: rgb(1, 21, 22);
}
</style>
