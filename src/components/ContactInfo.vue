<template>
    <div class="contact-info">
      <h2>Contact</h2>
      <div class="address">
        <p>123 Fifth Avenue, New York, NY 10160</p>
        <p>Email: contact@info.com</p>
        <p>Phone: 929-242-6868</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ContactInfo'
  };
  </script>
  
  <style scoped>
  /* Add your CSS styling for the ContactInfo component here */
  .contact-info {
    font-size: 16px;
  }
  
  .address {
    margin-top: 20px;
  }
  
  .address p {
    margin: 5px 0;
  }
  </style>
  