
<template>
    <div class="dashboard__container">
      <Header class="dashboard__header"></Header>
      <div class="dashboard__container-inner">
        <div class="dashboard__container-left">
          <MenuBar></MenuBar>
          <UpgradeAdd></UpgradeAdd>
        </div>
        <div class="dashboard__container-content">
          <div class="dashboard__container-contenter">
            <Title title="Ticketing"></Title>
            <div class="dashboard__container-wrapper">
                <div class="dashboard__container-wrapper-left">
                    <TicketCards />
                    <Transaction />
                </div>
                <div class="dashboard__container-wrapper-right">
                    <Agenda/>
                </div>
            </div>
          </div>  
        </div>
      </div>
    </div>
  </template>
  
  <script>
    import Agenda from './components/Agenda.vue'
    import Header from './components/Header.vue'
    import MenuBar from './components/MenuBar.vue'
    import TicketCards from './components/TicketCards.vue'
    import Title from './components/Title.vue'
    import Transaction from './components/Transaction.vue'
  
    export default {
        name: 'App',
        components: {
        Header,
        MenuBar , 
        Title , 
        TicketCards ,
        Transaction , 
        Agenda
        }
    }
  </script>
  
  <style scoped>
    *{
        box-sizing: border-box;
        padding: 0;
        margin:0;
    }
    body{
        color: navy;
        font-family: Verdana, Geneva, Tahoma, sans-serif;
    }
    .dashboard__container{
      width: 97.5% ; 
      margin: 0 0 0 2.5% ; 
    }
    .dashboard__container-inner{
      display: flex ;
    }
    .dashboard__container-left{
      padding-right: 30px ; 
    }
    .dashboard__container-content{
      background: #f5f5f5;
      width: 100% ;
    }
    .dashboard__container-contenter{
      padding: 3vh 30px; 
    }
    .dashboard__container-wrapper{
        display: flex; 
        gap: 3% ; 
    }
    .dashboard__container-wrapper-left{
        width: 67% ; 
    }
    .dashboard__container-wrapper-right{
        width: 30% ;
    }
</style>
  
    
  