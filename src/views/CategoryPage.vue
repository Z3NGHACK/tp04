<template>
    <div class="container">
      <div class="header">
        <Header/>
      </div>
      <div class="navbar">
        <div class="btn">
          <i class="ri-gallery-view-2"></i>
          Browse All Categories
          <i class="ri-arrow-down-s-line"></i>
        </div>
        <div class="navC">
          <div><Navbar class="nav" nav="Hot Deal" :categoryId="1" icon="ri-fire-line" /></div>
          <div><Navbar class="nav" nav="Home" :categoryId="2"/></div>
          <div><Navbar class="nav" nav="Food" :categoryId="3" icon="ri-arrow-down-s-line"/></div>
          <div><Navbar class="nav" nav="Vegetable" :categoryId="4"  icon="ri-arrow-down-s-line"/></div>
          <div><Navbar class="nav" nav="Drink" :categoryId="5"/></div>
          <div><Navbar class="nav" nav="Cookies" :categoryId="6"/></div>
          <div><Navbar class="nav" nav="Meat & Seafood" :categoryId="7" icon="ri-arrow-down-s-line"/></div>
          <div><Navbar class="nav" nav="Bakery" :categoryId="8"/></div>
        </div>
      </div>
      <div class="dealBoard">
        <DealBoard/>
      </div>
      <h1>Category Page</h1>
      <p>Details for Category ID: {{ categoryId }}</p>
    </div>
</template>

<script>
import { useRoute } from 'vue-router';
import Navbar from '@/components/Navbar.vue';
import Header from '@/components/Header.vue';
import DealBoard from '@/components/DealBoard.vue';

export default {
  components:{
    Navbar,
    Header,
    DealBoard
  },
  setup() {
    const route = useRoute();
    return {
      categoryId: route.params.categoryId,
    };
  },
};
</script>
<style scoped>
.container{
  width: 1520px;
  margin: 0 auto;
  padding: 2rem;
}
.navbar{
  display: flex;
  align-items: center;
  gap: 30px;
  margin: 20px 0;
  height: 80px;
}
.navbar div{
  height: 40px;
}
.navC{
  display: flex;
  align-items: center;
}
.navbar .nav{
  width: 140px;
  white-space: nowrap;
}
.btn{
  background-color: #3BB77E;
  padding: 5px 15px;
  border-radius: 5px;
  color: #fff;
  display: flex;
  gap: 5px;
  align-items: center;
}
</style>
  