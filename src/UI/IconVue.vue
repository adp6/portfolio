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
    :deep(.popper) {
        background: rgb(199, 155, 78);
        padding: 20px;
        border-radius: 20px;
        color: black;
        font-weight: bold;
    }

    :deep(.popper #arrow::before) {
        background: #e92791;
    }

    :deep(.popper:hover),
    :deep(.popper:hover > #arrow::before) {
        background: #4d7bc4;
        color: rgb(209, 209, 209);
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