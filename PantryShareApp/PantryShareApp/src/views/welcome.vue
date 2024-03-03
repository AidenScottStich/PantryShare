<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'


const menuClicked = ref(false);
const navStyle = ref("")

const toggleMenu = function () {
  menuClicked.value = !menuClicked.value;
  navStyle.value = menuClicked.value ? "fade-inflate-fast" : "fade-deflate-fast";
}
</script>

<template>
  <div class="position-relative">
    <!-- Floating Images -->
    <img src="@/assets/orange.png" alt="Shape 1" class="floating-image shape-1">
    <img src="@/assets/can.png" alt="Shape 2" class="floating-image shape-2">
    <img src="@/assets/pineapple.png" alt="Shape 3" class="floating-image shape-3">
    <img src="@/assets/blues.png" alt="Shape 4" class="floating-image shape-4">
    <img src="@/assets/lettuce.png" alt="Shape 5" class="floating-image shape-5">
    <img src="@/assets/can.png" alt="Shape 6" class="floating-image shape-6">
    <img src="@/assets/banana.png" alt="Shape 7" class="floating-image shape-7">
    <img src="@/assets/strawberry.png" alt="Shape 8" class="floating-image shape-8">
    <img src="@/assets/blues.png" alt="Shape 9" class="floating-image shape-9">
    <img src="@/assets/greens.png" alt="Shape 10" class="floating-image shape-10">

    <div class="container mt-5">
      <div class="card mt-5 mx-auto position-relative" style="max-width: 400px; z-index: 2;">
        <!-- Display the imported image (Logo) -->
        <img :src="importedLogo" alt="Logo" class="logo mx-auto d-block" style="margin-top: 0px; max-width: 100%; height: auto;">

        <div class="card-body text-center"> <!-- Centering all text elements -->
          <h1 class="card-title">Welcome</h1>
          
          <p class="card-text">Matching people in need with people who can help</p>

          <!-- Login and Sign Up Buttons -->
          <div class="mt-4">
            <div class="mb-2">
              <a href="#" class="btn btn-primary">Login</a>
            </div>
            <p class="card-text">or</p>
            <div>
              <a href="#" class="btn btn-success" style="margin-bottom: 75px;">Sign Up</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// Import the image using the require function
import yourLogo from '@/assets/logo.png';

export default {
  data() {
    return {
      // Store the imported image path
      importedLogo: yourLogo,
    };
  },
};
</script>

<style>
.position-relative {
  position: relative;
}

.floating-image {
  position: absolute;
  max-width: 100%;
  max-height: 100%;
}

.shape-1 {
  width: 100px;
  top: -10%;
  left: 50%;
  transform: rotate(45deg);
}

.shape-2 {
  width: 80px;
  top: 50%;
  left: 85%;
  transform: rotate(100deg);
}

.shape-3 {
  width: 120px;
  top: -10%;
  left: 90%;
  transform: rotate(-5deg);
}

.shape-4 {
  width: 120px;
  top: 20%;
  left: 90%;
  transform: rotate(60deg);
}

.shape-5 {
  width: 120px;
  top: -13%;
  left: -15%;
  transform: rotate(210deg);
}

.shape-6 {
  width: 120px;
  top: 15%;
  left: -15%;
  transform: rotate(-60deg);
}

.shape-7 {
  width: 120px;
  top: 75%;
  left: 85%;
  transform: rotate(-15deg);
}

.shape-8 {
  width: 120px;
  top: 35%;
  left: -15%;
  transform: rotate(-25deg);
}

.shape-9 {
  width: 120px;
  top: 65%;
  left: -11%;
  transform: rotate(-100deg);
}

.shape-10 {
  width: 120px;
  top: 85%;
  left: -15%;
  transform: rotate(-40deg);
}

.floating-image {
  position: absolute;
  max-width: 100%;
  max-height: 100%;
  animation: fadeIn 1s ease-in-out; /* Apply fade-in animation */
}

@keyframes fadeIn {
  from {
    opacity: 0; /* Start with zero opacity */
  }
  to {
    opacity: 1; /* End with full opacity */
  }
}

.logo {
  position: relative;
  z-index: 1;
  animation: flyIn 1s ease-in-out; /* Apply fly-in animation */
}

@keyframes flyIn {
  from {
    transform: translateY(-100%); /* Start above the viewport */
    opacity: 0; /* Start with zero opacity */
  }
  to {
    transform: translateY(0); /* End at its normal position */
    opacity: 1; /* End with full opacity */
  }
}

html, body {
  overflow: hidden; /* Prevent scrolling */
}

.position-relative {
  position: relative;
  height: 100vh; /* Set the height to 100% of the viewport height */
 /* Hide any content that overflows the fixed view */
}

/* Add shapes 4 to 10 with appropriate sizes, positions, and rotations */
</style>
