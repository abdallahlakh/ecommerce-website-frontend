<template>
    <div class="top-navbar">
      <div class="company-name">hook</div>
      <div class="search-bar">
        <input v-model="searchQuery" placeholder="Search for products">
        <button @click="search">Search</button>
      </div>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    name: 'TopNavbar',
  
    setup() {
      const searchQuery = ref('');
      
      const search = () => {
        // Implement your search logic here.
        console.log(`Searching for: ${searchQuery.value}`);
        // You can navigate to a search results page or perform an API call here.
      };
  
      return {
        searchQuery,
        search,
      };
    },
  };
  </script>
  
  <style scoped>
  /* Add your CSS styling here */
  .top-navbar {
    background-color: #333;
    color: #fff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 30px;
  }
  
  .company-name {
    font-size: 18px;
    font-weight: bold;
  }
  
  .search-bar {
    display: flex;
    align-items: center;
  }
  
  .search-bar input {
    padding: 5px;
    margin-right: 10px;
    border: 1px solid #ccc;
  }
  
  .search-bar button {
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
  }
  
  .search-bar button:hover {
    background-color: #0056b3;
  }
  </style>
  