<template>
  <div>
    <button @click="toggle">rerender by instance</button>
    <div ref="parent">
      <child></child>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import Child from "./Child.vue";

export default {
  name: "Key",
  components: {
    Child
  },
  methods: {
    toggle() {
      this.$refs["parent"].textContent = null;
      const ComponentClass = Vue.extend(Child);
      const instance = new ComponentClass();
      instance.$mount();
      this.$refs["parent"].appendChild(instance.$el);
    }
  }
};
</script>
