<script>
import Category from '../components/Category.vue';
import Promotion from '../components/Promotion.vue';

export default {
  components: {
    Category,
    Promotion,
  },
  data() {
    return {
      categories: [
        {id: 2, image: '/image/apple.png', name: 'Red Apple', itemCount: 68 , backgroundColor: '#FEEFEA'},
        {id: 3, image: '/image/snake.png', name: 'Snake', itemCount: 34 , backgroundColor: '#FFF3EB'},
        {id: 1, image: '/image/cakeandmilk.png', name: 'Cake & Milk', itemCount: 14 , backgroundColor: '#F2FCE4'},
        {id: 4, image: '/image/plum.png', name: 'Black Plum', itemCount: 25 , backgroundColor: '#FFF3FF'},
        {id: 5, image: '/image/peach.png', name: 'Peach', itemCount: 17 , backgroundColor: '#FFFCEB'},
        {id: 6, image: '/image/kiwi.png', name: 'Oganic Kiwi', itemCount: 21 , backgroundColor: '#ECFFEC'},
        {id: 7, image: '/image/cabbage.png', name: 'Vegetables', itemCount: 65 , backgroundColor: '#F2FCE4'},
        {id: 8, image: '/image/headphone.png', name: 'Headphone', itemCount: 34 , backgroundColor: '#FFFCEB'},
        {id: 9, image: '/image/milk&cake.png', name: 'Milk & Cake', itemCount: 53, backgroundColor: '#F2FCE4'},
        {id: 10, image: '/image/orange.png', name: 'Orange', itemCount: 63, backgroundColor: '#FFF3FF' },
      ],
      promotions: [
        {id: 101, title: 'Everyday Fresh & Clean with Our Products', 
        image: '/image/onion.png', width: 200,backgroundColor: '#F0E8D5'},
        {id: 102, title: 'Make your Breakfast Healthy and Easy', 
        image: '/image/milk.png', width: 150, backgroundColor: '#F3E8E8'},
        {id: 103, title: 'The best Organic Products Online', 
        image: '/image/vegetables.png', width: 240, backgroundColor: '#E7EAF3'}
      ]
    }
  }
};
</script>

<template>
  <div id="home">
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
</style>
