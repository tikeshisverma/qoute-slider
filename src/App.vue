<template>
  <div class="container" id="app">
    <Slider v-bind:quotes="quotes" />
  </div>
</template>

<script>
import Slider from "./components/slider.vue";
export default {
  name: "app",
  data() {
    return {
      quotes: [
        "That's one small step for a man, one giant leap for mankind - Neil Armstrong",
        "The Universe is under no obligation to make sense to you - Neil deGrasse Tyson",
        "I would like to die on Mars. Just not on impact - Elon Musk",
        "If we can conquer space, we can conquer childhood hunger - Buzz Aldrin",
        "The eternal silence of these infinite spaces frightens me - Blaise Pascal"
      ]
    };
  },
  methods: {},
  created() {},
  components: { Slider }
};
</script>

<style>
html,
body {
  height: 100%;
}
#app {
  height: 100%;
}
</style>
