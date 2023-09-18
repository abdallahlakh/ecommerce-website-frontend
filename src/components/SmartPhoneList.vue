<template>
  <div>
    <h1 class="page-title">Smart Phone Products</h1>
    <div class="product-container">
      <router-link
        v-for="product in smartPhoneProducts"
        :key="product.id"
        :to="{ name: 'product', params: { category:'SmartPhone',id: product.id } }"
        class="product-item"
      >
        <div class="product-image">
          <img :src="require('@/assets/air.jpg')" alt="Product Image" />
        </div>
        <div class="product-details">
          <h2 class="product-title">{{ product['Product Title'] }}</h2>
          <p class="product-price">Price: {{ product.Price }}</p>
        </div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SmartPhoneList',
  props: {
    smartPhoneProducts: Array,
  },
};
</script>

<style scoped>
.page-title {
  font-size: 24px;
  margin-top: 20px;
  margin-bottom: 20px;
  position: relative;
  top: 10ch;
}

.product-container {
  display: flex;
  position: relative;
  top: 15ch;
  flex-wrap: wrap;
  justify-content: flex-start;
  gap: 0;
}

.product-item {
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 10px;
  transition: transform 0.2s;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  min-width: 200px;
  max-width: 200px;
  display: flex;
  flex-direction: column;
}

.product-item:hover {
  transform: translateY(-5px);
}

.product-image {
  max-width: 100%;
  flex-grow: 1;
  overflow: hidden;
  text-align: center;
}

.product-image img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
  border-radius: 5px;
}

.product-details {
  margin-top: 10px;
}

.product-title {
  font-size: 14px;
  margin: 5px 0;
}

.product-price {
  font-size: 12px;
  color: #777;
}
</style>
