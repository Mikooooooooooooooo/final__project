<template> 
    <div class="ticketcards">
        <TicketCard v-for="card in cards" :title="card.title" :count="card.count" />
    </div>
</template>

<script>
    import TicketCard from './TicketCard.vue';

    export default{ 
        data() {
            return { 
                cards: [
                    {   title: 'Ticket Solds' , count:'11.720' } , 
                    {   title: 'Ticket Refund' , count: '2.345' } , 
                    {   title: 'Canceled' , count: '980' } , 
                    {   title: 'Rescheduled' , count: '720' } , 
                ]
            }
        } , 
        components: {
            TicketCard
        }
    }
</script>

<style scoped>
    .ticketcards{
        display: flex ; 
        gap: 2% ;
        margin: 3vh 0 ; 
    }
</style>