<template>
    <div class="card-container">
        <div class="main-info-container">
            <img src="..//assets/Item 1.png" alt="">
            <p>1234 5678 9012 3456</p>
        </div>
        <div class="cardholder-info">
            <p class="card-info">Card Holder</p>
            <p class="name">Nella Vitta</p>
        </div>
    </div>
</template>

<style>
.card-container{
    width: 300px;
    height: 200px;
    background: rgb(54,59,100);
    background: linear-gradient(-45deg, rgba(54,59,100,1) 15%, rgba(239,109,77,1) 59%, rgba(239,200,104,1) 100%);

    display: flex;
    flex-direction: column;
    justify-content: space-between;

    padding: 30px;
    color: white;

}

.main-info-container{
    display: flex;
    flex-direction: column;
    font-size: 20px;

}
.main-info-container img{
    width: 25px;
    height: 25px;
    margin-bottom: 10px;
}
.card-info{
    font-size: 10px;
    margin-bottom: 10px;
}


</style>