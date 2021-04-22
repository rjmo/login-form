<template>
  <div></div>
</template>

<script>
// @ is an alias to /src

export default {
  beforeCreate: function() {
    document.body.className = "home";
  },
  name: "Home",
  components: {},
};
</script>

<style scoped>
body {
  background-color: wheat;
  max-height: 100%;
}
</style>
