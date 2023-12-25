<template>
    <div class="pagination">
        <img src="../assets/prev.svg" alt="" @click="prev()" class="pagination__prev">
        <div class="pagination__icon">
            {{ current - 1 }}
        </div>
        <div class="pagination__icon">
            {{ current  }}
        </div>
        <div class="pagination__icon">
            {{ current + 1}}
        </div>
        <img src="../assets/next.svg" @click="next()" alt="" class="pagination__next">
    </div>
</template>

<script>
    export default{
        props: ['min' ,'max'] , 
        data () {
            return {
                current: this.min 
            }
        } , 
        methods: {
            prev() {
                if (this.current !== this.min) {
                    this.current--;
                    this.$emit('click', this.current);
                }
            },
            next() {
                if (this.current !== this.max) {
                    this.current++;
                    this.$emit('click', this.current);
                }
            }
        }
    }
</script>

<style>
    .pagination{
        display: flex; 
        gap: 10px; 
    }
    .pagination__icon{
        width: 40px ;
        height: 40px ; 
        text-align: center ; 
        line-height: 40px; 
        background: rgba(239, 109, 77, 0.2) ; 
        color: #ef6d4d ; 
    }
    .pagination__icon:nth-of-type(2){
        background: #ef6d4d ; 
        color: white ;
    }
</style>