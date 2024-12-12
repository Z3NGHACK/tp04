<template>
    <link
    href="https://cdn.jsdelivr.net/npm/remixicon@4.5.0/fonts/remixicon.css"
    rel="stylesheet"
    />
    <div class="containerD">
        <h2>Don't miss amazing grocery deals</h2>
        <span>Sign up for daily newletter</span>
        <div class="sub">
            <div class="let">
                <i class="ri-telegram-2-line"></i>
                <span>Your email address</span>
            </div>
            <div class="btn">
                <button>subscribe</button>
            </div>
        </div>
    </div>
</template>
<style scoped>
.containerD{
    display: flex;
    flex-direction: column;
    background-image: url('/image/bg.jpg');
    background-size: cover;
    background-position: center; 
    background-repeat: no-repeat;
    height: 300px;
    border-radius: 10px;
    justify-content: center;
    padding-left: 80px;
}
h2{
    font-size: 3rem;
    font-weight: 600;
}
span{
    color: #555555;
    font-size: 2rem;
}
.sub{
    display: flex;
    align-items: center;
    color: #747474;
    font-size: 1.5rem;
    border: 1px solid #747474;
    width: 400px;
    border-radius: 100px;
    margin-top: 20px;
    padding-left: 5px;
    height: 50px;
}
.let{
    width: 70%;
    display: flex;
    align-items: center;
}
.sub span{
    font-size: 1rem;
}
.btn{
    width: 30%;
    justify-content: end;
    display: flex;
    align-items: end;
    border-radius: 50px;
}
.btn button{
    height: 50px;
    font-size: 0.8rem;
    width: 100%;
    border: none;
    border-radius: 100px;
    padding: 10px 10px;
    background-color: #3BB77E;
    color: #fff;
}

</style>