<template>
  <div>
    <button @click="toggle">rerender by emit instance</button>
    <div ref="parent">
      <emit-child @echo="echo"></emit-child>
    </div>
    <p v-if="echo">echo: {{ text }}</p>
  </div>
</template>

<script>
import Vue from "vue";
import EmitChild from "./EmitChild.vue";

export default {
  name: "Key",
  components: {
    EmitChild
  },
  data() {
    return {
      text: ""
    };
  },
  methods: {
    toggle() {
      this.$refs["parent"].textContent = null;
      const ComponentClass = Vue.extend(EmitChild);
      const instance = new ComponentClass();
      instance.$mount();
      instance.$on("echo", e => this.echo(e));
      this.$refs["parent"].appendChild(instance.$el);
    },
    echo(e) {
      this.text = e;
    }
  }
};
</script>
