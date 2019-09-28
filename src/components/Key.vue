<template>
  <div>
    <button @click="toggle">rerender by key</button>
    <child :key="key"></child>
  </div>
</template>

<script>
import Child from "./Child.vue";

export default {
  name: "Key",
  components: {
    Child
  },
  data() {
    return {
      key: 0
    };
  },
  methods: {
    toggle() {
      this.key = this.key ? 0 : 1;
    }
  }
};
</script>
