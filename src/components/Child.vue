<template>
  <div>
    <p>{{ count }}</p>
    <button @click="increment">+ 1</button>
  </div>
</template>

<script>
export default {
  name: "Child",
  data() {
    return {
      count: 0
    };
  },
  methods: {
    increment() {
      this.count++;
    }
  }
};
</script>
