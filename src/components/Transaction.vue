<template>
    <div class="transaction">
        <div class="transaction__header">
            <div class="transaction__title">
                Latest Transaction
            </div>
            <div class="dropdawn">
                <div class="dropdawn__top" v-on:click="show = !show">
                    <div class="dropdawn__title">
                        {{ title }}
                    </div>
                    <img src="../assets/down.png"  alt=""  class="dropdawn__button">
                </div>
                <div v-if="show" v-for="(button , index) in buttons" v-on:click="swap(index)" class="dropdawn__bottom">
                    {{ button }}
                </div>
            </div>

        </div>
        <div class="transaction__list">
            <TransactionItem v-for="item in story" :item="item" > </TransactionItem>
        </div>
        <div class="transaction__footer">
            <div class="transaction__footer-title">
                Showimg 1-5 from 100 data
            </div>
            <Pagination @click="changeList" :min="1" :max="5" />
        </div>
    </div>
</template>

<script scoped>
    import Pagination from './Pagination.vue';
    import TransactionItem from './TransactionItem.vue';
    export default{
        data() {
            return {
                buttons: ['Prev Month', 'Next Month'],
                buttonss: ['Prev Month', 'Next Month'] , 
                title: 'This Month'  , 
                show: false  , 
                story: [
                    {title: 'Music Event' , date:'12 June 2021' , email:'nadia@gmail.com' , amount: '-$ 60,00' , type:'compeleted' , color:'#50C878' , background:'rgba(80, 200, 120, 0.2)'} ,
                    {title: 'Anime Music Event' , date:'12 June 2021' , email:'sam@gmail.com' , amount: '-$ 60,00' , type:'compeleted',color:'#50C878' , background:'rgba(80, 200, 120, 0.2)'} ,
                    {title: 'Webinar Event' , date:'12 June 2021' , email:'will@gmail.com' , amount: '-$ 60,00' , type:'pending', color:' #ef6d4d' , background:'rgba(239, 109, 77, 0.2)'} ,
                    {title: 'UX Design Workshop' , date:'12 June 2021' , email:'samantha@gmail.com' , amount: '-$ 60,00' , type:'compeleted', color:'#50C878' , background:'rgba(80, 200, 120, 0.2)'} ,
                    {title: 'Music Event' , date:'12 June 2021' , email:'soap@gmail.com' , amount: '-$ 60,00' , type:'pending',color:' #ef6d4d' , background:'rgba(239, 109, 77, 0.2)'} ,
                    {title: 'Design Event' , date:'12 June 2021' , email:'jack@gmail.com' , amount: '-$ 60,00' , type:'compeleted', color:'#50C878' , background:'rgba(80, 200, 120, 0.2)'} ,
                    {title: 'Music Event' , date:'12 June 2021' , email:'jordan@gmail.com' , amount: '-$ 60,00' , type:'Unpaid',color:' #DC143C' , background:'rgba(220, 20, 60, 0.2)'  } ,
                ] ,
                storyList: [
                    [
                        { title: 'Tech Conference', date: '11 June 2021', email: 'nadia@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                        { title: 'Coding Workshop', date: '11 June 2021', email: 'sam@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                        { title: 'Webinar', date: '11 June 2021', email: 'will@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                        { title: 'UX Design Seminar', date: '11 June 2021', email: 'samantha@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                        { title: 'Frontend Development Talk', date: '11 June 2021', email: 'soap@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                        { title: 'Digital Marketing Workshop', date: '11 June 2021', email: 'jack@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                        { title: 'AI in Business Symposium', date: '11 June 2021', email: 'jordan@gmail.com', amount: '-$ 60,00', type: 'unpaid', color: '#DC143C', background: 'rgba(220, 20, 60, 0.2)' },
                    ],
                    [
                        { title: 'Music Festival', date: '12 June 2021', email: 'nadia@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                        { title: 'Anime Expo', date: '12 June 2021', email: 'sam@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                        { title: 'Web Development Bootcamp', date: '12 June 2021', email: 'will@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                        { title: 'UI/UX Design Challenge', date: '12 June 2021', email: 'samantha@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                        { title: 'Digital Art Exhibition', date: '12 June 2021', email: 'soap@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                        { title: 'Product Management Summit', date: '12 June 2021', email: 'jack@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                        { title: 'Code Jam', date: '12 June 2021', email: 'jordan@gmail.com', amount: '-$ 60,00', type: 'unpaid', color: '#DC143C', background: 'rgba(220, 20, 60, 0.2)' },
                    ],
                    [
                        { title: 'Startup Pitch Competition', date: '13 June 2021', email: 'emma@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                        { title: 'Art Showcase', date: '13 June 2021', email: 'oliver@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                        { title: 'Virtual Reality Workshop', date: '13 June 2021', email: 'emma@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                        { title: 'Graphic Design Tutorial', date: '13 June 2021', email: 'emma@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                        { title: 'Blockchain Summit', date: '13 June 2021', email: 'emma@gmail.com', amount: '-$ 60,00', type: 'unpaid', color: '#DC143C', background: 'rgba(220, 20, 60, 0.2)' },
                        { title: 'AI in Healthcare Conference', date: '13 June 2021', email: 'sarah@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                        { title: 'Product Launch Event', date: '13 June 2021', email: 'john@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                    ] ,
                    [{ title: 'Networking Mixer', date: '14 June 2021', email: 'john@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                    { title: 'Digital Health Symposium', date: '14 June 2021', email: 'mary@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                    { title: 'Startup Funding Workshop', date: '14 June 2021', email: 'david@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                    { title: 'E-commerce Trends Talk', date: '14 June 2021', email: 'linda@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                    { title: 'Networking Mixer', date: '14 June 2021', email: 'john@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                    { title: 'Digital Health Symposium', date: '14 June 2021', email: 'mary@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                    { title: 'Startup Funding Workshop', date: '14 June 2021', email: 'david@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                    ] , 
                    [ 
                    { title: 'AI and Ethics Panel', date: '15 June 2021', email: 'alex@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                    { title: 'Marketing Analytics Workshop', date: '15 June 2021', email: 'emma@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                    { title: 'AI and Ethics Panel', date: '15 June 2021', email: 'alex@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                    { title: 'Marketing Analytics Workshop', date: '15 June 2021', email: 'emma@gmail.com', amount: '-$ 60,00', type: 'pending', color: '#ef6d4d', background: 'rgba(239, 109, 77, 0.2)' },
                    { title: 'Frontend Frameworks Conference', date: '15 June 2021', email: 'michael@gmail.com', amount: '-$ 60,00', type: 'unpaid', color: '#DC143C', background: 'rgba(220, 20, 60, 0.2)' },
                    {title: 'Placeholder Event 12', date: '15 June 2021', email: 'placehol@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },
                    { title: 'Frontend Frameworks Conference', date: '15 June 2021', email: 'michael@gmail.com', amount: '-$ 60,00', type: 'unpaid', color: '#DC143C', background: 'rgba(220, 20, 60, 0.2)' },
                    { title: 'Marketing Workshop', date: '15 June 2021', email: 'julia@gmail.com', amount: '-$ 60,00', type: 'completed', color: '#50C878', background: 'rgba(80, 200, 120, 0.2)' },  
                ]
                ]
            }
        } , 
        components: {
            TransactionItem ,
            Pagination
        } ,
        methods: {
            swap(index) {
                const temp = this.title ; 
                this.title = this.buttons[index] ; 
                this.buttons[index] = temp ; 
                if (this.title == "This Month"){
                    this.changeItem(0)
                }
                if (this.title == "Prev Month"){
                    this.changeItem(1)
                    
                }
                if (this.title == "Next Month"){
                    this.changeItem(2)
                }
            } , 
            changeItem(index){
                this.styles = this.styles_list[index]
                this.amount = this.amounts[index]
                this.percent = this.percents[index]
            }  ,
            changeList(index) {
                console.log(" cdscs"  + index)
                if (index >= 0 && index <=5 )
                    this.story = this.storyList[index - 1];
        }
        }
    }
</script>

<style scoped>

    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap') ; 
    
    .transaction{
        padding: 30px; 
        background: white; 
    }
    .transaction__header{
        display: flex;  
        justify-content: space-between;
    }
    .transaction__header-r{
        display: flex; 
        gap: 10px; 
    }
    .transaction__title{
        font-family: 'Open Sans' ,  sans-serif ; 
        font-weight: 600 ;
        font-size: 22px; 
        color: navy ; 
    }
    .transaction__list{
        margin-bottom: 4vh ; 
    }
    .transaction__footer{
        display: flex ; 
        justify-content: space-between;
    }
    .transaction__footer-title{
        color: rgba(0, 0, 0, 0.7) ; 
        font-size: 14px ; 
    }
    .dropdawn{
        border: 1px solid  rgba(0, 0, 0, 0.7);
    }
    
    .dropdawn__top{
        display: flex ; 
        padding: 10px 15px; 
        width: 140px ; 
        justify-content: space-between ;
        cursor: pointer;
    }
    .dropdawn__title{
        font-size: 14px;
        font-weight: 500;
        font-family: 'Open Sans' , sans-serif;
        color: navy;
    }
    .dropdawn__button{
        width: 20px ; 
        height: 20px ; 
    }
    .dropdawn__bottom{
        padding: 10px 15px; 
        width: 140px ; 
        font-size: 14px;
        font-weight: 500;
        font-family: 'Open Sans' , sans-serif;
        color: navy;    
        cursor: pointer ; 
    }
   
    .dropdawn__bottom:hover{
        background: #ededed; 
    }
</style>