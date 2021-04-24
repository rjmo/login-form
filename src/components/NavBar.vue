<template>
  <div class="topnav" id="myTopnav">
    <!-- <a href=""><img src="../assets/logo_quattrocentos.svg" alt=""></a> -->
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-link to="/login">Login</router-link>
    <a class="icon" @click="respNav()">
      <i class="fa fa-bars"></i>
    </a>
  </div>
</template>

<script>
export default {
    name: 'NavBar',
    methods: {
    /* Toggle between adding and removing the "responsive" class to topnav when the user clicks on the icon */
    respNav() {
      var x = document.getElementById("myTopnav");
      if (x.className === "topnav") {
        x.className += " responsive";
      } else {
        x.className = "topnav";
      }
    },
  },
};
</script>

<style>
.topnav {
  overflow: hidden;
  background-color: #FBF9FF;
  font-family: 'Open Sans', sans-serif;
  /* font-family: 'Orelega One', cursive; */
  z-index: 1;
  }

.topnav a {
  float: left;
  display: block;
  color: #517664;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
  transition: 0.2s;

}

.topnav a:hover {
  background-color: rgb(255, 255, 255);
  color: black;
  transition: 0.2s;
}

.topnav .icon {
  display: none;
}

@media screen and (max-width: 600px) {
  .topnav a:not(:first-child) {
    display: none;
  }
  .topnav a.icon {
    float: right;
    display: block;
  }
}

@media screen and (max-width: 600px) {
  .topnav.responsive {
    position: relative;
  }
  .topnav.responsive .icon {
    position: absolute;
    right: 0;
    top: 0;
  }
  .topnav.responsive a {
    float: none;
    display: block;
    text-align: left;
  }
}
</style>