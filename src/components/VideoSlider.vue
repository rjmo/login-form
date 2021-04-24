<template>
  <div>
    <div class="slideshow-container">
      <!-- Full-width images with number and caption text -->
      <div class="mySlides fade">
        <img
          src="https://via.placeholder.com/950X150

C/O https://placeholder.com/ "
        />
      </div>

      <div class="mySlides fade">
        <img src="img2.jpg" />
      </div>

      <div class="mySlides fade">
        <img src="img3.jpg" />
      </div>

      <!-- Next and previous buttons -->
 
      <div>

        <a class="prev" @click="plusSlides(-1)">&#10094;</a>
        <a class="next" @click="plusSlides(1)">&#10095;</a>
      </div>


    </div>
    <br />
  </div>
</template>

<script>
var slideIndex = 1;
export default {
  name: "VideoSlider",
  methods: {
    plusSlides(n) {
      this.showSlides((slideIndex += n));
    },
    showSlides(n) {
      var i;
      var slides = document.getElementsByClassName("mySlides");
      if (n > slides.length) {
        slideIndex = 1;
      }
      if (n < 1) {
        slideIndex = slides.length;
      }
      for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";
      }
      slides[slideIndex - 1].style.display = "block";
    },
  },
};
</script>

<style scoped>
img {
  vertical-align: middle;
}

.slideshow-container {
  min-height: 50vh;
  margin: auto;
  position: relative;
  /* position: absolute;
  top: 55%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%); */
  min-width: 80vw;
  min-height: 67vh;
  background: gray;
}

.mySlides {
  display: none;
}

.prev,
.next {
  cursor: pointer;
  position: absolute;
  top: 45%;
  width: auto;
  margin-top: -22px;
  padding: 16px;
  color: rgb(255, 255, 255);
  font-weight: bold;
  font-size: 18px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
  user-select: none;
}

/* Position the "next button" to the right */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

/* On hover, add a black background color with a little bit see-through */
.prev:hover,
.next:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

/* Caption text */
.text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 100%;
  text-align: center;
}

/* Fading animation */
.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}

@-webkit-keyframes fade {
  from {
    opacity: 0.4;
  }
  to {
    opacity: 1;
  }
}

@keyframes fade {
  from {
    opacity: 0.4;
  }
  to {
    opacity: 1;
  }
}

/* On smaller screens, decrease text size */
@media only screen and (max-width: 300px) {
  .prev,
  .next {
    font-size: 11px;
  }
}
</style>
