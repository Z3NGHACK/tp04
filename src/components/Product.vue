<template>
    <div class="container">
        <div class="img">
            <img :src="image" alt="#">
        </div>
        <span>Hodo Food</span>
        <h3>{{ title }}</h3>
        <span class="star"><img src="/image/star.png" alt="#">(4.0)</span>
        <span>500 gram</span>
        <div class="bot">
            <div class="price">
                <h3>$2.51</h3>
                <span class="priceS">$2.5</span>
            </div>
            <div class="btn" @click="navToProductPage">
                <button  @click="handleNavigate">Add <i>+</i></button>
            </div>
        </div>
    </div>
</template>
<script>
export default{
    props:{
        title: String,
        image: String,
        productId: [String, Number]
    },
    methods:{
        handleNavigate() {
            this.$router.push({ name: 'ProductDetailPage', params: { productId: this.productId } });
        }
    }
}
</script>
<style scoped>
    .container{
        display: flex;
        flex-direction: column;
        border-radius: 10px;
        border: 1px solid #e5e5e5;
        width: 270px;
        padding: 20px;
    }
    h3{
        font-size: 0.9rem;
        font-weight: 600;
    }
    img{
        width: 150px;
    }
    .img{
        display: flex;
        justify-content: center;
        padding: 20px 0;
    }
    .star{
        display: flex;
        align-items: center;
    }
    .star img{
        width: 80px;
    }
    span{
        color: #7e7e7e;
    }
    .bot{
        display: flex;
        
    }
    .price{
        display: flex;
        align-items: center;
        gap: 5px;
        width: 50%;
    }
    .price h3{
        color: #3BB77E
    }
    button{
        background-color: #DEF9EC;
        border: none;
        border-radius: 5px;
        padding: 10px 20px;
    }
    .btn{ 
        width: 50%;
        display: flex;
        justify-content: end;
    }
    .btn i{
        padding-left: 10px;
    }

</style>