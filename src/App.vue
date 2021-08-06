<template>
  <Calendar />
</template>

<script>
import "@/assets/main.css";
import Calendar from "./views/Calendar.vue";
export default {
  components: {
    Calendar,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
