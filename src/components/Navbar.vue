<template>
    <div class="container">
      <span @click="handleNavigate">
        <i v-if="icon" :class="icon"></i>
        {{ nav }}
      </span>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      nav: {
        type: String,
        default: "Default Navigation",
      },
      categoryId: {
        type: [String, Number],
        default: null,
      },
      icon: {
        type: String, 
        default: null,
      },
    },
    methods: {

      handleNavigate() {
        if (this.categoryId) {
          this.$router.push({
            name: "CategoryPage",
            params: { categoryId: this.categoryId },
          });
        } else {
          console.error("categoryId is not defined.");
        }
      },
    },
  };
  </script>
  
<style scoped>
.container{
    padding: 5px 15px;
    border-radius: 5px;
    transition: 0.2s ease;
    cursor: pointer;
    margin-bottom: 20px;
    height: 40px;
    display: flex;
    justify-content: center;
    font-size: 0.8rem;
}
.container:hover{
    background-color: #3BB77E;
    color: #fff;
}

.container span {
    display: flex;
    align-items: center;
    gap: 8px; 
}
</style>