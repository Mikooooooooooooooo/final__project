<template>
    <div class="payment-container">
        <h3>Quick Payment</h3>
        <div class="user">
            <img src="../assets/jolie.jpg" alt="">
            <div class="user-info">
                
                <p class="name">Nadila Adja</p>
                <p class="amount">$ 12.587,80</p>
            </div>
            <p class="date">09/09/21</p>
        </div>
        <div class="user">
            <img src="../assets/jolie.jpg" alt="">
            <div class="user-info">
                <p class="name">Nadila Adja</p>
                <p class="amount">$ 12.587,80</p>
            </div>
            <p class="date">09/09/21</p>
        </div>
        <button class="transfer-btn">New Transfer</button>
    </div>
</template>

<style scoped>
.payment-container{
    margin-top: 30px;
    width: 300px;
    height: 350px;

    display: flex;
    flex-direction: column;
    padding: 15px 15px;

    justify-content: space-between;
    background-color: white;
}
.user{
    width: 100%;
    height: 30%;

    background-color: #f5f5f5;

    display: flex;
    flex-direction: row;
    padding: 20px 15px;

    justify-content: center;
    
}
.user-info{
    display: flex;
    flex-direction: column;
}
.name, .amount{
    padding: 0 10px;
}
.name{
    font-size: 13px;
}
.amount{
    font-weight: 600;
    padding-top: 5px;
    font-size: 18px;
}
.date{
    padding-left: 25px;
}
.user-info {

}
.user img{
    width: 30px;
    height: 30px;

    border-radius: 30px;
}

.transfer-btn{
    border: transparent;
    background-color: #ef6d4d;
    padding: 15px 10px;
    color: white;
    font-family: 'Montserrat', sans-serif;
    font-weight: bold;
}
</style>