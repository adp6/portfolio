<template>
    <button @click="func">
        {{ name }}
    </button>
</template>

<style scoped>
    button{
        border: none;
        cursor: pointer;
        border-radius: 25px;
        height: 60px;
        width: 200px;
        font-size: 1.5em;
        font-family: "Poppins",sans-serif;
        font-weight: 700;
        background-color: #4d7bc4;
        color: white;
        transition: .4s;
    }
    button:hover{
        background-color: rgb(199, 155, 78);
        color: black;
    }
    @media screen and (max-width:900px) {
        button{
            width: 100px;

        }
    }
</style>
<script>
    export default {
        name:'ButtonVue',
        props:{
            name:String,
            func:Function
        }
    }
</script>