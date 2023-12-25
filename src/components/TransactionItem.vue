<template>
    <div class="transactionItem">
        <div class="transactionItem__icon">
            <img src="../assets/exchange.svg" alt="">
        </div>
        <div class="transaction__text">
            <div class="transaction__title">
                {{ item.title }}
            </div>
            <div class="transaction__date">
                {{ item.date }}
            </div>
        </div>
        <div class="transaction__email">
            {{ item.email }}
        </div>
        <div class="transaction__status">
            <TransactionStatus :title="item.type" :background="item.background" :color="item.color"></TransactionStatus>
        </div> 
        <div class="transaction__amount">
            {{ item.amount }}
        </div>
    </div>
</template>

<script>
    import TransactionStatus from './TransactionStatus.vue';

    export default{
        props:['item'] , 
        components: {
            TransactionStatus
        }
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap') ; 
    .transactionItem{
        display: flex; 
        margin: 2vh 0 ; 
        font-family: 'Open Sans' , sans-serif ; 

    }   
    .transaction__text{
        width: 25% ; 
        margin-right: 3% ;
    }
    .transactionItem__icon{
        margin-right: 20px ; 
        padding: 10px; 
        border: 1px rgba(0, 0, 0, 0.7) solid ;
        background: #ef6d4d;
    }
    .transaction__title{
        font-weight: 600 ; 
        font-size: 18px ;
        margin-bottom: 2px ; 
        color: navy ; 
    }
    .transaction__date{
        font-size: 14px; 
        color: rgba(0, 0, 0, 0.7);
    }
    .transaction__email{
        width: 25%  ; 
        line-height: 40px; 
    }
    .transaction__amount{
        color: #ef6d4d; 
        font-size: 20px ; 
        font-weight: 600; 
        line-height: 40px;
    }
   
    
</style>