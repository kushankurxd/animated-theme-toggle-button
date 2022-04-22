<template>
  <div>
    <input type="checkbox" id="toggle" />
    <label for="toggle" class="button" @click="toggleTheme"></label>
  </div>
</template>

<script>
export default {
  name: "ToggleButtonComponent",
  data() {
    return {
      status: 0,
    };
  },
  methods: {
    toggleTheme: function () {
      this.status = this.status === 0 ? 1 : 0;
      this.$emit("toggleTheme", this.status);
    },
  },
};
</script>

<style scoped>
#toggle {
  display: none;
}

.button {
  display: inline-block;
  width: 90px;
  height: 35px;
  background-color: #f58840;
  border-radius: 30px;
  position: relative;
  cursor: pointer;
}

.button::after {
  content: url("../assets/sun-line.svg");
  width: 40px;
  height: 40px;
  background-color: #e03c3c;
  border: 2px solid #f58840;
  border-radius: 50%;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.25);
  position: absolute;
  top: -5px;
  left: 0;
  display: grid;
  place-content: center;
  line-height: 0;
  transition: background-color 1s, transform 1s ease-in;
}

#toggle:checked + .button::after {
  content: url("../assets/moon-line.svg");
  background-color: #1f257f;
  transform: translateX(50px) rotate(360deg);
}
</style>
