<template>
    <div class="menu-bar">
        <MenuItem v-for="(item, index) in elements" :key="index" :itemName="item.itemName" :imageName="item.imageName"></MenuItem>
        <a class="menu-item" href="../../index3.html" id="menu-item" :style="{ backgroundColor: background, color: textColor }"
            @mouseover="isMouseOver = true"
            @mouseleave="isMouseOver = false">
            <img src="../assets/Item 7.svg" alt="">
            <p>Banking</p>
        </a> 
        <a class="menu-item" href="../../index.html" id="menu-item" :style="{ backgroundColor: background, color: textColor }"
            @mouseover="isMouseOver = true"
            @mouseleave="isMouseOver = false">
            <img src="../assets/Item 7.svg" alt="">
            <p>Dashboard</p>
        </a> 
    </div>
</template>

<script scoped>
    import MenuItem from './MenuItem.vue';

    export default{
        components:{
            MenuItem
        },
        data(){
            return{
                elements: [
                    {itemName: 'Email', imageName: 'Item 2.svg'},
                    {itemName: 'Contacts', imageName: 'Item 3.svg'},
                    {itemName: 'Crypto', imageName: 'Item 4.svg'},
                    {itemName: 'Kanban', imageName: 'Item 5.svg'},
                    {itemName: 'Invoicing', imageName: 'Item 6.svg'},
                    {itemName: 'Ticketing', imageName: 'Item 12.svg'},
                    {itemName: 'File Manager', imageName: 'Item 8.svg'},
                    {itemName: 'User', imageName: 'Item 9.svg'},
                    {itemName: 'Calendar', imageName: 'Item 10.svg'},
                    {itemName: 'Todo List', imageName: 'Item 11.svg'},
                ], 
                isMouseOver: false , 
            };
        },
        computed: {
            background() {
                return this.isMouseOver ? 'rgba(255, 127, 80, 0.3)' : '';
            },
            textColor() {
                return this.isMouseOver ? 'rgb(255, 106, 69)' : 'rgba(0, 0, 0, 0.7)';
            }
        } 
    }
</script>

<style scoped>
    .menu-item {
        display: flex;
        padding: 10px;
        width: 180px;
        height: 50px;
        align-items: center;
        font-size: 14px;
        color: rgba(0, 0, 0, 0.7);
        cursor: pointer;
        z-index: 1;
    }
    .menu-item p{
        z-index: 2;
    }
    .menu-item img{
        width: 20px;
        height: 20px;
        margin-right: 15px;
    }
</style>