<template>
    <div>
        <Popper hover :content=name>
            <img :src=icon :alt=name>
        </Popper>
    </div>
</template>

<style scoped>
    img{
        padding: 10px;
        width: v-bind(width);
        background-color: #212529;
    }
    img:hover{
        background-color: #4d7bc4;
        transition: 1s;
    }
    div{
        display: inline-block;
    }
   
</style>

<script>
import Popper from "vue3-popper";
export default {
    name:'IconVue',
    props:{
        icon:String,
        name:String,
        width:String
    },
    components:{
        Popper
    }
}
</script>