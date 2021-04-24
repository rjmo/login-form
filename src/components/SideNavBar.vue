<template>
  <div id="app">
    <div>
      <div id="mySidenav" class="sidenav" style="width: 60px;">
        <i
          class="fa fa-chevron-circle-left fa-5"
          aria-hidden="true"
          @click="openClose()"
        ></i>
        <a href="#"><img src="" alt=""/></a>
        <a href="#"><img src="" alt=""/></a>
        <a href="#"><img src="" alt=""/></a>
        <a href="#"><img src="" alt=""/></a>
      </div>
      <!-- Use any element to open the sidenav -->

      <!-- Add all page content inside this div if you want the side nav to push page content to the right (not used if you only want the sidenav to sit on top of the page -->
      <div id="main">
        <div class="top">
        <VideoSlider />

        </div>
      </div>
    </div>

    <router-view></router-view>
  </div>
</template>

<script>
import VideoSlider from '../components/VideoSlider.vue';
export default {
  name: "SideNavBar",
  components: {
    VideoSlider
  },
  methods: {
    /* Set the width of the side navigation to 250px and the left margin of the page content to 250px */
    openClose() {
      let nav = document.getElementById("mySidenav").style.width;
      if (nav == "60px") {
        document.getElementById("mySidenav").style.width = "200px";
        document.getElementById("main").style.marginLeft = "200px";
      } else if (nav == "200px") {
        document.getElementById("mySidenav").style.width = "60px";
        document.getElementById("main").style.marginLeft = "60px";
      }
    },
  },
};
</script>

<style>
.sidenav {
  height: 100%; /* 100% Full-height */
  position: fixed; /* Stay in place */
  left: 0;
  background-color: #19241f; /* Black*/
  overflow-x: hidden; /* Disable horizontal scroll */
  padding-top: 60px; /* Place content 60px from the top */
  transition: 0.5s; /* 0.5 second transition effect to slide in the sidenav */
  display: flex;
  flex-flow: column;
  justify-content: start;
}

/* The navigation menu links */
.sidenav a {
  padding: 8px 8px 8px 0px;
  text-decoration: none;
  font-size: 25px;
  color: #a6b8b2;
  transition: 0.3s;
  margin-left: 10px;
}

.sidenav img {
  border-radius: 30px;
  width: 40px;
  height: 40px;
}

/* When you mouse over the navigation links, change their color */
.sidenav a:hover {
  color: #f1f1f1;
}

/* Position and style the close button (top right corner) */
.sidenav .closebtn {
  position: absolute;
  top: 0;
  right: 25px;
  font-size: 36px;
  margin-left: 50px;
}

/* Style page content - use this if you want to push the page content to the right when you open the side navigation */
#main {
  transition: margin-left 0.5s;
  margin-left: 60px;
}

.top {
  max-height: 50vh;
  background-color:aqua;
}

/* On smaller screens, where height is less than 450px, change the style of the sidenav (less padding and a smaller font size) */
@media screen and (max-height: 450px) {
  .sidenav {
    padding-top: 15px;
  }
  .sidenav a {
    font-size: 18px;
  }
}
</style>
