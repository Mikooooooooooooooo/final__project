<template scoped>
    <div class="container">
        <div class="heading">
            <p class="container-header">Latest Transactions</p>
            <div class="buttons">
                <SimpleButton title="This Month" imageName="down.png"></SimpleButton>
                <img class="more-button" src="../assets/more.png" alt="">
            </div>
        </div>
        <div class="history-container"><UsersHistory></UsersHistory></div>

        <div class="footer-container">
            <p>Showing 1-5 from 100 data</p>
            <div class="footer-buttons">
                <img class="arrow-button" src="../assets/left-arrow.png" alt="">
                <div class="number-button">1</div>
                <div class="number-button-2">2</div>
                <div class="number-button">3</div>
                <img class="arrow-button" src="../assets/right-arrow.png" alt="">
            </div>
        </div>
    </div>
</template>

<script scoped>
import SimpleButton from './SimpleButton.vue';
import UsersHistory from './UsersHistory.vue';
export default{
    components:{
        SimpleButton,
        UsersHistory
    }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

.container{
    width: 100%;
    height: 600px;
    padding: 30px ;
    background-color: white;
    display: flex;
    flex-direction: column;
}
.heading{
    width: 100%;
    height: 20%;

    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 30px;
    
}
.container-header{
    color: #363b64;
    font-size: 20px;
    font-weight: bold;
}

.footer-container{
    widows: 100%;
    height: 20%;

    padding-top: 30px;

    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
}

.footer-container p{
    font-size: 12px;
}

.buttons{
    width: 25%;
    height: 100%;
    display: flex;
    flex-direction: row;

    align-items: center;
    align-content: center;
}


.more-button{
    width: 25px;
    height: 25px;
    margin: 12px;
}


.number-button{
    background-color: #fbeeea;
    color: #ef6d4d;
    width: 40px;
    height: 40px;
    margin: 5px;
    font-size: 15px;
    display: flex;
    align-items: center;
    justify-content: center;

}
.number-button-2{
    display: flex;
    background-color:  #ef6d4d;
    color: #fbeeea ;
    width: 40px;
    height: 40px;
    margin: 5px;
    font-size: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.footer-buttons{
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
}
.arrow-button{
    width: 30px;
    height: 30px;
}
.history-container{
    width: 100%;
    height: 500px;
}

</style>