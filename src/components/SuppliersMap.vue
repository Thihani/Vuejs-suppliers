<template>
  <div id="app">
    <Map 
    :suppliers ="suppliers" />
  </div>
</template>

<script>
import Map from "./Map";
export default {
  name: "SuppliersMap",
  components: {
    Map
  },
  props: ['suppliers'],
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0px 100px;
}
</style>