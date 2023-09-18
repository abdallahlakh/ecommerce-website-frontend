<template>
  <div class="product-gallery">
    <table class="product-table">
      <tbody>
        <tr v-for="(row, rowIndex) in productRows" :key="rowIndex">
          <td v-for="(product, columnIndex) in row" :key="columnIndex">
            <div class="product-item" @click="handleProductClick(product.title)">
              <img :src="product.image" :alt="product.title" class="product-image" />
              <div class="product-title">{{ product.title }}</div>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'ProductGallery',
  props: {
    products: Array, // An array of product objects with 'title' and 'image' properties
  },
  computed: {
    productRows() {
      // Split products into rows with 4 columns each
      const rows = [];
      for (let i = 0; i < this.products.length; i += 4) {
        rows.push(this.products.slice(i, i + 4));
      }
      return rows;
    },
  },
  methods: {
    handleProductClick(productName) {
      console.log(`Clicked on product: ${productName}`);
      
      // Get the corresponding section by ID
      const sectionId = productName.toLowerCase() + 'Section'; // Assuming product names match IDs
      console.log(sectionId)
      // Scroll to the section
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' }); // Smooth scrolling
      }
    },
  },
};
</script>

<style scoped>
/* Add your CSS styling here */
.product-gallery {
  position: relative;
  top: 10ch;
  text-align: center;
}

.product-table {
  border-collapse: collapse;
  width: 80%; /* Adjust the width as needed */
  margin: 0 auto;
  background-color: white;
}

.product-table td {
  border: 1px solid white;
  padding: 10px;
}

.product-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 10px;
  cursor: pointer; /* Add a pointer cursor to indicate clickable elements */
}

.product-image {
  max-width: 100%;
  height: auto;
  width: 100px; /* Set a fixed width for all images (adjust as needed) */
  height: 100px; /* Set a fixed height for all images (adjust as needed) */
}

.product-title {
  margin-top: 10px;
  font-size: 14px; /* Adjust the font size to make them smaller */
  color: #333; /* Set the text color */
}
</style>
