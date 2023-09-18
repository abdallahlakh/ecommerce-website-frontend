<template>
  <div class="image-navbar">
    <div class="image-logo">
      <div class="flex-container">
        <img src="@/assets/home.jpg" alt="Home" style="display: flex; height: 672px; width: 1800px;" />
      </div>
    </div>
    <div class="announcement-container">
      <Anouncement /> <!-- Include the Anouncement component here -->
    </div>
  </div>
</template>

<script>
import Anouncement from './Anouncement.vue'; // Import the Anouncement component

export default {
  name: 'ImageNavbar',
  components: {
    Anouncement, // Include the Anouncement component in the components section
  },
};
</script>

<style scoped>
/* Add your CSS styling here */
.image-navbar {
  background-color: hsl(0, 0%, 13%);
  display: flex;
  justify-content: center;
  align-items: center;
  height: 672px;
  position: relative;
  top: -1ch;
}

/* Center the Anouncement component */
.announcement-container {
  position: absolute;
  top: 50%; /* Move the top of the container to the middle of the parent */
  left: 85%; /* Move the left of the container to the middle of the parent */
  transform: translate(-50%, -50%); /* Center the container using translate transform */
  background-color: rgba(255, 255, 255, 0.7);
  padding: 10px 20px;
  width: 400px;
  height: 400px;
  border-radius: 5px;
  z-index: 1;
}
</style>
