<template>
  <nav class="navbar">
    <div class="logo">Categories</div>
    <div class="nav-links">
      <div class="dropdown-wrapper">
        <button @mouseover="showAllProductsDropdown = true">All Products</button>
        <div v-if="showAllProductsDropdown" class="dropdown">
          <button @click="navigate('Air Conditioner')">Air Conditioner</button>
          <button @click="navigate('Home Appliances')">Home Appliances</button>
          <button @click="navigate('Audio & Video')">Audio & Video</button>
          <button @click="navigate('Refrigerator')">Refrigerator</button>
          <button @click="navigate('New Arrivals')">New Arrivals</button>
        </div>
      </div>
      <button @click="navigate('Todays Deals')">Todays Deals</button>
      <button @click="navigate('Gift Cards')">Gift Cards</button>
      <button @click="navigate('Shopping Cart')">
        <i class="fas fa-shopping-cart"></i> Shopping Cart ({{ cartItems.length }})
      </button>
      <button @click="navigate('Log In')">Log In</button>
    </div>
  </nav>
</template>


<style scoped>
/* Add your CSS styling here */
.navbar {
  background-color: #333;
  color: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  

}

.logo {
  font-size: 24px;
  font-weight: bold;
}

.nav-links button {
  background: none;
  border: none;
  color: #fff;
  cursor: pointer;
  font-size: 16px;
  margin-right: 20px;
}

.nav-links button:hover {
  text-decoration: underline;
}

.dropdown-wrapper {
  position: relative;
  display: inline-block;
}

.dropdown {
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #333;
  display: none;
  flex-direction: column;
  width: 150px; /* Adjust the width as needed */
  z-index: 1; /* Ensure the dropdown appears above other elements */
}

.dropdown button {
  width: 100%;
  padding: 10px;
  text-align: left;
  border: none;
  background: none;
  color: #fff;
  cursor: pointer;
  font-size: 16px;
}

.dropdown button:hover {
  background-color: #555;
}

.dropdown-wrapper:hover .dropdown {
  display: block;
}
</style>

  <script>
  import '@fortawesome/fontawesome-free/css/all.css'; // Import FontAwesome CSS

  import { ref } from 'vue';
  
  export default {
    name: 'MainNavbar',
  
    setup() {
      const cartItems = ref([]);
      const showAllProductsDropdown = ref(false);
  
      const navigate = (category) => {
        // Implement your navigation logic here.
        console.log(`Navigating to ${category}`);
      };
  
      return {
        cartItems,
        showAllProductsDropdown,
        navigate,
      };
    },
  };
  </script>
  
  
