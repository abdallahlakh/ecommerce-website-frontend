<template>
  <div class="announcement">
    <p class="announcement-text">The best home entertainment system is here</p>
    <button @click="shopNow" class="shop-button">Shop now</button>
  </div>
</template>

<script>
export default {
  name: 'Anouncement',
  setup() {
    const shopNow = () => {
      // Implement your logic for handling the "Shop now" button click here
      console.log('Shop now clicked');
      // You can add navigation logic or other actions here.
    };

    return {
      shopNow,
    };
  },
};
</script>

<style scoped>
/* Add your CSS styling here */
.announcement {
  text-align: center;
  color: #333; /* Set the text color */
  font-size: 24px; /* Adjust the font size (example: 24px) */
  position: relative;
  top: 50%; /* Center vertically */
  transform: translateY(-50%);
}

/* Style for the announcement text */
.announcement-text {
  margin-bottom: 20px; /* Add spacing between text and button */
}

/* Style for the shop button */
.shop-button {
  background-color: #007BFF;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.shop-button:hover {
  background-color: #0056b3;
}
</style>
