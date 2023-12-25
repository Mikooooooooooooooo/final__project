<template scoped>
    <div class="button-container">
        <p>{{title}}</p>
        <img class="button-img" src="../assets/icon1.svg">
    </div>
</template>

<script scoped>
    export default{
        props:{
            title: {
                type: String,
                require: true
            },
            imageName: {
                type: String,
                required: true
            },
        }
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

    .button-container{
        width: 120px;
        padding: 10px;
        height: 40px;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;

        font-weight: 100;
        font-family: 'Montserrat', sans-serif;
        font-weight: 100;
        font-size: 13px;
        color: #363b64;

        border: 1px solid #bebeca;
    }
    .button-img{
        width: 15px;
        height: 15px;
    }
    
</style>