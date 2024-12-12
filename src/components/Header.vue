<template>
    <div class="container">
        <img src="/image/logo.jpg" alt="#">
        <div class="search">
            <h2>All Category</h2>
            <i class="ri-arrow-down-s-line"></i>
            <div class="line"></div>
            <span>Search for items<i class="ri-search-line"></i></span>
            
        </div>
        <div class="infor_nav">
            <div class="acc">
                <i class="ri-account-circle-line"></i>
                Account
            </div>
            <div class="Compare">
                <i class="ri-bubble-chart-line"></i>
                Compare
            </div>
            <div class="Wishlist">
                <i class="ri-heart-line"></i>
                Wishlist
            </div>
            <div class="cart">
                <i class="ri-shopping-cart-2-line"></i>
                Cart
            </div>
        </div>
    </div>
</template>
<style scoped>
.container{
    display: flex;
    align-items: center;
    padding: 20px;
    height: 100px;
    gap: 30px;
    border-bottom: 1px solid #acacac;
    margin-bottom: 20px;
}
.search{
    font-size: 0.8rem;
    width: 30%;
    border-radius: 5px;
    padding: 10px;
    border: 1px solid #acacac;
    display: flex;
}
.infor_nav{
    display: flex;
    gap: 30px;
    width: 60%;
    justify-content: end;
}
h2{
    font-size: 0.8rem;
    font-weight: 600;
}
.search i{
    margin: 0 10px;
}
.line{
    border-left: 1px solid #cecece;
}
span{
    padding: 0 10px;
    position: relative;
    width: 70%;
}
span i{
    position: absolute;
    right: -5px;
    padding-left: 110px;
}
</style>