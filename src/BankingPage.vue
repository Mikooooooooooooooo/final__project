<template>
    <Header></Header>
    <section class="main">
        <MenuBar></MenuBar>
        <div class="banking-section">
            <h1 class="section-header">Banking</h1>
            <div class="center-part">
                <BalanceOverview></BalanceOverview>
                <LatestTransactions></LatestTransactions>
            </div>
            <div class="right-part">
                <CardItem></CardItem>
                <QuickPayment></QuickPayment>
    
            </div>
        </div>
    </section>
</template>
  
<script>
    import Header from './components/Header.vue';
    import MenuBar from './components/MenuBar.vue';
    import BalanceOverview from './components/BalanceOverview.vue';
    import LatestTransactions from './components/LatestTransactions.vue';
    import CardItem from './components/CardItem.vue';
    import QuickPayment from './components/QuickPayment.vue';

    export default {
        name: 'App',
        components: {
            Header,
            MenuBar,
            BalanceOverview,
            LatestTransactions,
            CardItem,
            QuickPayment,
        }
    }
</script>
  
<style>
    *{
        box-sizing: border-box;
        padding: 0;
        margin:0;
    }
    body{
        color: #324461;
        font-family: Verdana, Geneva, Tahoma, sans-serif;
    }
    .main{
        padding: 0% 2%;
        display: flex;
        flex-direction: row;
        height: 100%;
        font-family: 'Montserrat', sans-serif;
    }
    
    .banking-section{
        display: grid;
        width: 100%;
        background-color: #f5f5f5;
        padding: 30px;
        justify-content: space-between;
        position: relative;
        height: 100%;
    }
    
    .center-part{
        width: 800px;
        height: 100%;
        position: relative;

        grid-row: 2;
        grid-column: 1;

    }

    .section-header{
        grid-row: 1;
        grid-column: 1;
    }
    .right-part{
        grid-row: 2;
        grid-column: 2; 

        widows: 300px;
        height: 100%;

        margin-top: 30px;
        justify-content: space-between;
        
    }


</style>
  