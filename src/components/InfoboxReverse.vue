<template scoped>
    <div class="reverse-box" id="reverse-box">
        <p class="header"> {{infoHeader}}</p>
        <p class="description">{{infoDescription}}</p>
    </div>
</template>

<script>
    export default{
        name: 'InfoboxReverse',
        el: '#reverse-box',
        props:{
            infoHeader: String,
            infoDescription: String
        }
    }
</script>

<style scoped>
    .reverse-box{
        display: flex;
        flex-direction: column;
        width: 100%;
        height: 30%;
    }
    .header{
        font-size: 100%;
        font-weight: 200;
        color: #807b8b;
        padding-bottom: 5%;
    }
    .description {
        font-weight: 600;
        font-size: 150%;
    }
</style>