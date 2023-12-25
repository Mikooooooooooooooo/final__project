<template>
    <div class="transactionStatus">
        <div class="transactionStatus__title" :style="{color: color ,  background: background}">
            {{ title }}
        </div>
    </div>
</template>

<script>
    export default{ 
       props:['title' ,'color' , 'background']
    }
</script>

<style>
    .transactionStatus{
        width: 140px ; 
        font-weight: 600 ;  
        margin-right: 100px ;
    }
    .transactionStatus__title{
        padding: 10px 0 ; 
        text-align: center ;
    }
</style>