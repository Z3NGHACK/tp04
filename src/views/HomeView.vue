<script>
import Category from '../components/Category.vue';
import Promotion from '../components/Promotion.vue';
import PopProduct from '../components/Product.vue';
import DealBoard from '@/components/DealBoard.vue';
import Navbar from '@/components/Navbar.vue';
import Header from '@/components/Header.vue';

export default {
  components: {
    Category,
    Promotion,
    PopProduct,
    DealBoard,
    Navbar,
    Header
  },
  data() {
    return {
      categories: [
        {id: 11, image: '/image/apple.png', name: 'Red Apple', itemCount: 68 , backgroundColor: '#FEEFEA'},
        {id: 12, image: '/image/snake.png', name: 'Snake', itemCount: 34 , backgroundColor: '#FFF3EB'},
        {id: 13, image: '/image/cakeandmilk.png', name: 'Cake & Milk', itemCount: 14 , backgroundColor: '#F2FCE4'},
        {id: 14, image: '/image/plum.png', name: 'Black Plum', itemCount: 25 , backgroundColor: '#FFF3FF'},
        {id: 15, image: '/image/peach.png', name: 'Peach', itemCount: 17 , backgroundColor: '#FFFCEB'},
        {id: 16, image: '/image/kiwi.png', name: 'Oganic Kiwi', itemCount: 21 , backgroundColor: '#ECFFEC'},
        {id: 17, image: '/image/cabbage.png', name: 'Vegetables', itemCount: 65 , backgroundColor: '#F2FCE4'},
        {id: 18, image: '/image/headphone.png', name: 'Headphone', itemCount: 34 , backgroundColor: '#FFFCEB'},
        {id: 19, image: '/image/milk&cake.png', name: 'Milk & Cake', itemCount: 53, backgroundColor: '#F2FCE4'},
        {id: 20, image: '/image/orange.png', name: 'Orange', itemCount: 63, backgroundColor: '#FFF3FF' },
      ],
      promotions: [
        {id: 101, title: 'Everyday Fresh & Clean with Our Products', 
        image: '/image/onion.png', width: 200,backgroundColor: '#F0E8D5'},
        {id: 102, title: 'Make your Breakfast Healthy and Easy', 
        image: '/image/milk.png', width: 150, backgroundColor: '#F3E8E8'},
        {id: 103, title: 'The best Organic Products Online', 
        image: '/image/vegetables.png', width: 240, backgroundColor: '#E7EAF3'}
      ],
      popProducts: [
        {id: 1, title: 'Seeds of Change Organic Quinoa Brown, & Red Rice', image: 'image/onion.png'},
        {id: 2, title: 'Seeds of Change Organic Quinoa Brown, & Red Rice', image: 'image/onion.png'},
        {id: 3, title: 'Seeds of Change Organic Quinoa Brown, & Red Rice', image: 'image/onion.png'},
        {id: 4, title: 'Seeds of Change Organic Quinoa Brown, & Red Rice', image: 'image/onion.png'},
        {id: 5, title: 'Seeds of Change Organic Quinoa Brown, & Red Rice', image: 'image/onion.png'},
      ],
    }
  }
};
</script>

<template>
  <link
    href="https://cdn.jsdelivr.net/npm/remixicon@4.5.0/fonts/remixicon.css"
    rel="stylesheet"
/>
  <div id="home">
    <div class="header">
      <Header/>
    </div>
    <div class="navbar">
      <div class="btn">
        <i class="ri-gallery-view-2"></i>
        Browse All Categories
        <i class="ri-arrow-down-s-line"></i>
      </div>
      <div class="nav"><Navbar nav="Hot Deal" :categoryId="1" icon="ri-fire-line" /></div>
      <div class="nav"><Navbar nav="Home" :categoryId="2"/></div>
      <div class="nav"><Navbar nav="Food" :categoryId="3" icon="ri-arrow-down-s-line"/></div>
      <div class="nav"><Navbar nav="Vegetable" :categoryId="4"  icon="ri-arrow-down-s-line"/></div>
      <div class="nav"><Navbar nav="Drink" :categoryId="5"/></div>
      <div class="nav"><Navbar nav="Cookies" :categoryId="6"/></div>
      <div class="nav"><Navbar nav="Meat & Seafood" :categoryId="7" icon="ri-arrow-down-s-line"/></div>
      <div class="nav"><Navbar nav="Bakery" :categoryId="8"/></div>
    </div>
    <div class="dealBoard">
      <DealBoard/>
    </div>
    <div class="category-card">
      <router-link
        v-for="(category, index) in categories"
        :key="index"
        :to="{ name: 'CategoryPage', params: { categoryId: category.id } }"
      >
        <Category
          :image="category.image"
          :name="category.name"
          :itemCount="category.itemCount"
          :backgroundColor="category.backgroundColor"
        />
      </router-link>
    </div>

    <div class="promotion-section">
        <Promotion
          v-for="(promotion, index) in promotions"
          :key="index"
          :title="promotion.title"
          :image="promotion.image"
          :backgroundColor="promotion.backgroundColor"
          :width="promotion.width"
          :productId="promotion.id"
          @view-detail="navigateToDetail"
        />
    </div>

    <div class="popProduct">
      <PopProduct
        v-for="(popProduct, index) in popProducts"
        :key="index"
        :title="popProduct.title"
        :image="popProduct.image"
        :productId="popProduct.id"
      />
    </div>
  </div>
</template>

<style scoped>
#home {
  display: flex;
  flex-direction: column;
}
.category-card {
  display: flex;
  justify-content: space-between;
  padding: 20px;
}
.promotion-section {
  display: flex;
  justify-content: space-between;
  padding: 20px;
  margin-top: 20px;
}
.popProduct{
  display: flex;
  justify-content: space-between;
  padding: 20px;
}
.navbar{
  padding: auto;
  display: flex;
  align-items: center;
  gap: 20px;
  color: #000;
  margin-bottom: 50px;
}
.navbar div{
  display: flex;
  height: 40px;
  justify-content: center;
}
.btn{
  background-color: #3BB77E;
  padding: 10px;
  border-radius: 5px;
  color: #fff;
  display: flex;
  gap: 5px;
  height: 40px;
  }
</style>
