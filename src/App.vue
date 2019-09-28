<template>
  <div id="app">
    <vif></vif>
    <key></key>
    <instance></instance>
  </div>
</template>

<script>
import Vif from "./components/Vif.vue";
import Key from "./components/Key.vue";
import Instance from "./components/Instance.vue";

export default {
  name: "app",
  components: {
    Vif,
    Key,
    Instance
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-flow: column;
}
</style>
