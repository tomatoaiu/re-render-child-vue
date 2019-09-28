<template>
  <div>
    <button @click="toggle">rerender by v-if</button>
    <child v-if="showChild"></child>
  </div>
</template>

<script>
import Child from "./Child.vue";

export default {
  name: "Vif",
  components: {
    Child
  },
  data() {
    return {
      showChild: true
    };
  },
  methods: {
    toggle() {
      this.showChild = false;
      this.$nextTick(() => (this.showChild = true));
    }
  }
};
</script>
