<template>
  <div class="product-view">
    <div class="product-detail">
      <div class="product-image">
        <!-- Assuming 'Product Image' is the URL to the product image -->
        <img :src="require('@/assets/refrigrator.jpg')" alt="Product Image" />
      </div>
      <div class="product-info">
        <h1 class="product-title">{{ product['Product Title'] }}</h1>
        <p class="product-price">{{ product['Price'] }}</p>
        <p class="product-description">{{ product['Product Description'] }}</p>
        <div class="product-features">
          <h2 class="features-title">Product Features</h2>
          <ul class="features-list">
            <!-- Assuming 'Product Features' is an array in your data -->
            <li v-for="feature in product['Product Features']" :key="feature">{{ feature }}</li>
          </ul>
        </div>
        <button class="add-to-cart-button" @click="addToCart(product['Product Title'])">Add to Cart</button>
      </div>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue';
import { useRoute } from 'vue-router';
import dbData from '@/data/db.json';

export default {
  name: 'ProductView',
  
  setup() {
    const route = useRoute();
    
    // Access the 'id' and 'category' route parameters
    const id = computed(() => route.params.id);
    const category = computed(() => route.params.category);

    // Replace this with your actual product data
    const product = computed(() => {
      // Simulate product data retrieval based on 'id' and 'category'
      // Replace this with your actual data source and logic
      const productData = [    
        { title: 'AirConditioner', data: dbData.AirConditioner },
        { title: 'Refrigerator', data: dbData.Refrigerator },
        { title: 'AudioVideo', data: dbData.Audiovideo },
        { title: 'SmartPhone', data: dbData.Smartphone },
        { title: 'KitchenAppliances', data: dbData.Kitchenappliances },
        { title: 'HomeAppliances', data: dbData.Homeappliances },
        { title: 'Pcs&Laptop', data: dbData.PCslaptop },
        { title: 'SmartHome', data: dbData.Smarthome }
      ];

      return productData.find(item => item.title === category.value)['data'].find(element=>element.id=id.value);
    });

    const addToCart = (pro) => {
      // Replace with your cart handling logic
      console.log('Product added to cart:', pro);
    };

    return {
      product,
      addToCart
    };
  },
};
</script>

<style scoped>
/* Add your CSS styling here */
.product-view {
  display: flex;
  background-color:beige;
  flex-direction: column;
  align-items: center;
  justify-content: center; /* Center content vertically */
  height: 100vh; /* Make the container fill the viewport height */
  margin: 20px;
}

.product-detail {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: space-between;
  margin-bottom: 20px;
  max-width: 800px; /* Add a maximum width to the content */
  width: 100%; /* Make the content responsive */
}

.product-image img {
  max-width: 200px;
  height: auto;
  border: 1px solid #ddd;
  padding: 5px;
  background-color: #f9f9f9;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.product-info {
  flex: 1;
  margin-left: 20px;
}

.product-title {
  font-size: 28px;
  margin: 10px 0;
}

.product-price {
  font-size: 24px;
  color: #f60;
  margin-bottom: 10px;
}

.product-description {
  font-size: 18px;
  margin: 10px 0;
}

.features-title {
  font-size: 20px;
  margin-top: 10px;
}

.features-list {
  font-size: 16px;
  margin-bottom: 20px;
  list-style-type: disc;
  padding-left: 20px;
}

.add-to-cart-button {
  padding: 15px 30px;
  background-color: #007bff;
  color: #fff;
  border: none;
  cursor: pointer;
  font-size: 20px;
  border-radius: 5px;
  transition: background-color 0.3s;
}

.add-to-cart-button:hover {
  background-color: #0056b3;
}
</style>
