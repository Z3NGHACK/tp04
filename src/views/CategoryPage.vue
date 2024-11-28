<template>
    <div>
      <h1>Category Page</h1>
      <p>Details for Category ID: {{ categoryId }}</p>
    </div>
  </template>
  
  <script>
  import { useRoute } from 'vue-router';
  
  export default {
    setup() {
      const route = useRoute();
      return {
        categoryId: route.params.categoryId,
      };
    },
  };
  </script>
  