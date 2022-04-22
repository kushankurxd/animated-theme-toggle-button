<template>
  <div
    class="container"
    :style="{ backgroundColor: status === 0 ? '#F0F0F0' : '#041C32' }"
  >
    <ToggleButtonComponent @toggleTheme="toggleTheme" />
  </div>
</template>

<script>
import ToggleButtonComponent from "../components/ToggleButton.vue";

export default {
  name: "IndexPage",
  components: {
    ToggleButtonComponent,
  },
  data() {
    return {
      status: 0,
    };
  },
  methods: {
    toggleTheme: function (status) {
      this.status = status;
    },
  },
};
</script>

<style scoped>
.container {
  background-color: #000;
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
