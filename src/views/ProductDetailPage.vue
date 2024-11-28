<template>
    <div>
      <h1>Product Detail Page</h1>
      <p>Details for Product ID: {{ productId }}</p>
    </div>
  </template>
  
  <script>
  import { useRoute } from 'vue-router';
  
  export default {
    setup() {
      const route = useRoute();
      return {
        productId: route.params.productId,
      };
    },
  };
  </script>
  