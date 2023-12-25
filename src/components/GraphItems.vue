<template scoped>
    <div class="container" id="container">
        <div class="element" id="element" :style="{ backgroundColor: backgroundColor, height: height, width:width }"></div>
        <p>{{elementName}}</p>
    </div>
</template>

<script scoped>
    export default{
        el: '#container',
        props:{
            elementName: String,
            backgroundColor: String,
            height: String,
            width: String
        }
    }
</script>

<style scoped>
    .container{
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        font-size: 70%;
        color: rgba(162,154,176,255);
        font-weight: 600;
    }
    .element{
        background-color: aqua;
        width: 70%;
        height: 100%;
        margin-bottom: 20%;
    }
</style>

