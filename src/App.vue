<template>
  <div id="app">
    <NavBar />
    <SideNavBar />
    <router-view></router-view>
  </div>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import SideNavBar from "./components/SideNavBar.vue";

export default {
  components: {
    NavBar,
    SideNavBar
  },
  methods: {},
};
</script>

<style></style>
