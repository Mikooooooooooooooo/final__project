<template scoped>
    <div class="container">
        <div class="top-container">
            <div class="text-info">
                <InformationBox infoHeader="Your Balance" infoDescription="June 1, 2020, 08:22 AM"></InformationBox>
                <div class="amount">
                    <InfoboxReverse infoHeader="This Month" infoDescription="$23,741.00"></InfoboxReverse>
                    <div class="percent-info">
                        <img src="../assets/up-arrow.png">
                        <p>+15%</p>
                    </div>
                </div>
            </div>
            <div class="graph-container">
                <WeeklyGraph class="weekGraph"></WeeklyGraph>
            </div>
        </div>

        <div class="bottom-container">
            <div class="el-1">
                <img src="../assets/income.png" alt="">
                <InfoboxReverse infoHeader="Income" infoDescription="$23,741.00"></InfoboxReverse>
            </div>
        <div class="el-1">
                <img src="../assets/income.png">
                <InfoboxReverse infoHeader="Outcome" infoDescription="$23,741.00"></InfoboxReverse>
            </div>
        </div>
    </div>
   
</template>

<script scoped>
    import InformationBox from './InformationBox.vue';
    import InfoboxReverse from './InfoboxReverse.vue';
    import WeeklyGraph from './WeeklyGraph.vue';

    export default{
        components:{
            InfoboxReverse,
            WeeklyGraph,
            InformationBox
        }
    }
</script>

<style scoped>
    .container{
        background-color: white;
        widows: 100%;
        height: 380px;
        display: flex;
        flex-direction: column;
        margin: 30px 0;
        padding: 30px;
    }

    .top-container{
        width: 100%;
        height: 2/3;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    .text-info{
        width: 1/3;
        height: 100%;

        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    
    .graph-container{
        width: 400px;
        height: 190px;
    }
    

    .percent-info{
        width: 50px;
        height: 30px;
        display: flex;
        flex-direction: row;
        color: #4cbc9a;
        font-weight: bolder;
        align-items: center;
        font-size: 15px;
        position: relative;
        padding-top: 45px;
    }
    .percent-info img{
        width: 20px;
        height: 20px;
        margin-right: 10px;
    }

    .el-1{
        display: flex;
        width: 250px;
        height: 130px;
        display: flex;
        flex-direction: row;
        align-content: center;
        position: relative;
        margin-right: 50px;
    }

    .el-1 img{
        width: 80px;
        height: 60px;
        padding-right: 20px;
    }
    .bottom-container{
        margin-top: 55px;
        width: 100%;
        height: 1/3;
        
        display: flex;
        flex-direction: row;
        justify-content: flex-start ;
    }
    

</style>

