<template scoped>
    
    <div class="userinfo-container">
        <div class="user">
            <img src="../assets//user.png" class="userImg" alt="">
            <p>{{nameSurname}}</p>
        </div>

        <p class="amount">{{amount}}</p>
        <p class="date">{{date}}</p>
        
        <div class="transaction-buttons">
            <img src="../assets/print.png" alt="">
            <img src="../assets/more.png" alt="">
        </div>
        
    </div>
</template>

<script scoped>
    export default{
        
        props:{
            imageName: String,
            nameSurname: String, 
            amount: String,
            date: String
        }
    }
</script>

<style scoped>
    .userinfo-container{
        width: 100%;
        height: 1/5;

        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 30px;
    }
    .amount, .date, .transaction-buttons{
        display: flex;
        width:1/4;
        
        
    }
    .userImg{
        width: 40px;
        height: 40px;
        border: 0px solid transparent;
        border-radius: 13px;
        margin-right: 20px;
    }
    .transaction-buttons img{
        width: 40px;
        height: 25px;
        padding-right: 15px;
    }
    .user{
        width: 200px;
        height: 100%;
        display: flex;
        flex-direction: row;
        align-items: center;
        font-weight:bold;
    }
</style>
