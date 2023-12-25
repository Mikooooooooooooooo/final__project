<template>
    <div class="ticketcard">
        <div class="ticketcard__top">
            <div class="ticketcard__icon">

            </div>
            <div class="ticketcard__title">
                {{ title }}
            </div>
        </div>

        <div class="ticketcard__count">
            {{ count }}
        </div>
    </div>
</template>

<script>
    export default{
        props: ['title' , 'count']
    }
</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

    .ticketcard{
        width: 20% ; 
        padding: 30px; 
        font-family: 'Open Sans' , sans-serif ; 
        background: white; 
    }
    .ticketcard__top{
        display: flex ; 
        gap: 10px    ; 
    }
    .ticketcard__icon{
        width: 7px;
        height: 7px; 
        background: #ef6d4d; 
        margin-top: 8px; 
    }
    .ticketcard__title{
        color: rgba(0, 0, 0, 0.7);
        font-size: 15px ; 
    }
    .ticketcard__count{
        color: navy ; 
        font-weight: 600 ; 
        font-size: 30px; 
    }
    
</style>