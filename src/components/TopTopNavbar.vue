<template>
    <div class="top-top-navbar">
      <div class="customer-service">24/7 Customer service 1-800-234-5678</div>
      <div class="links">
        <a href="#">Shipping & return</a>
        <a href="#">Track order</a>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'TopTopNavbar',
  };
  </script>
  
  <style scoped>
  /* Add your CSS styling here */
  .top-top-navbar {
    background-color: #333;
    color: #fff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 5px 20px;
  }
  
  .customer-service {
    font-size: 14px;
  }
  
  .links a {
    color: #fff;
    text-decoration: none;
    font-size: 14px;
    margin-right: 10px;
  }
  
  .links a:hover {
    text-decoration: underline;
  }
  </style>
  