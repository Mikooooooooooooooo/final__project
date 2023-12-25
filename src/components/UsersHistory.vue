<template scoped>
   <div class="users-container"> 
        <TransactionUser v-for="(item, index) in elements" :key="index" :imageName="item.imageName" :nameSurname="item.nameSurname" :amount="item.amount" :date="item.date"></TransactionUser>
    </div>
</template>

<script scoped>
import TransactionUser from './TransactionUser.vue';

export default{
    
    components:{
        TransactionUser
    },
    data(){
        return{
            elements: [
                {imageName: 'jolie.jpg', nameSurname: 'Portu Studio', amount:'$ 650,036.34', date:'Math 25, 2021'},
                {imageName: 'jolie.jpg', nameSurname: 'Akademi Studio', amount:'$ 650,036.34', date:'Math 25, 2021'},
                {imageName: 'jolie.jpg', nameSurname: 'Nextrun Studio', amount:'$ 650,036.34', date:'Math 25, 2021'},
                {imageName: 'jolie.jpg', nameSurname: 'Geex Studio', amount:'$ 650,036.34', date:'Math 25, 2021'},
                {imageName: 'jolie.jpg', nameSurname: 'Kleon Studio', amount:'$ 650,036.34', date:'Math 25, 2021'}
            ]
        }
    }
}
</script>

<style scoped>
    .users-container{
        width:100%;
        height: 100%;
        color: #363b64;
        
    }
    
    
</style>