<template>
    <a href="#Home"><img :src=arrow alt="arrow"></a>
    
</template>

<style scoped>
    img{
        width: 50px;
        padding: 10px;
        background-color: rgb(209, 209, 209);
        border-radius: 50px;
        position: fixed;
        bottom: 2%;
        right: 1%;
    }
</style>

<script>

import arrow from '../assets/arrow.svg'
export default {
    name:'ArrowVue',
    data(){
        return{
            arrow:arrow
        }
    }
}
</script>