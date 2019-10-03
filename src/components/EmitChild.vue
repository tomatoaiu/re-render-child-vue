<template>
  <div>
    <p>{{ count }}</p>
    <button @click="increment">+ 1</button>
    <button @click="emit">emit</button>
  </div>
</template>

<script>
export default {
  name: "EmitChild",
  data() {
    return {
      count: 0
    };
  },
  methods: {
    increment() {
      this.count++;
    },
    emit() {
      this.$emit("echo", this.count);
    }
  }
};
</script>
