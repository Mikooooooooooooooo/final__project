<template scoped>
    <div class="graph">
        <GraphItem class="elem" v-for="(element, index) in styles" 
            :key="index" 
            :elementName="element.elementName" 
            :backgroundColor="element.backgroundColor"
            :height="element.height"
            >
        </GraphItem>
        
    </div>
</template>

<script scoped>
    import GraphItem from './GraphItem.vue';

    export default {
        components: {
            GraphItem
        },
       
        data() {
            return {
                styles: [
                    {elementName: 'Mon', backgroundColor: 'rgba(241,199,103,255)', height: '80%'},
                    {elementName: 'Tue', backgroundColor: 'rgba(241,199,103,255)', height: '40%'},
                    {elementName: 'Wed', backgroundColor: 'rgba(241,199,103,255)', height: '35%'},
                    {elementName: 'Thu', backgroundColor: '#ef6d4d', height: '43%'},
                    {elementName: 'Fri', backgroundColor: 'rgba(241,199,103,255)', height: '30%'}, 
                    {elementName: 'Sat', backgroundColor: 'rgba(241,199,103,255)', height: '60%'},
                    {elementName: 'Sun', backgroundColor: '#ef6d4d', height: '65%'},
                ]
            };
        },
    }
</script>

<style scoped>
    .graph {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: row;
        
        margin: 2%;
        align-items: baseline;
    }
    
</style>
