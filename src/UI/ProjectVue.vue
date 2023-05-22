<template>
    <div class="row" :class="{hover:hover}">
        <div class="img">
            <img :src=img :alt=title @mouseover="()=>{this.hover=true}" @mouseout="()=>{this.hover=false}">
        </div>
        <div>
            <h2>{{ title }}</h2>
            <div class="skill">
                <div v-for="skill in skills" :key=skill.id>
                    <IconVue :icon=skill.img :name=skill.name width="60px"/>
                </div>
            </div>
            
            <p>
                {{ description }}
            </p>
            <a :href=github target="_blank">github</a><br>
            <a :href=link target="_blank">github Pages</a>
        </div>
    </div>
    
</template>


<script>
import IconVue from './IconVue.vue';
export default {
    name:'ProjectVue',
    props:{
        title:String,
        img:String,
        description:String,
        link:String,
        github:String,
        skills:Array
    },
    components:{
        IconVue
    },
    data(){
        return{
            hover:false
        }
    }
}
</script>

<style scoped>
p{
    margin-top: 1em;
    margin-bottom: 1.2em;
    overflow-wrap: anywhere;
    width: 100%;
    font-size: 1.3em;
}
a{
    font-size: 1.4em;
}
h2{
   font-size: 2.8em;
   font-weight: 900;
}
.skill{
    display: flex;
    flex-wrap: wrap;
    gap: 2%;
    margin: 20px 0 30px 0px;
}
.img{
    z-index: 200;
}
img{
    width:130%;
    transition: .4s;
}
img:hover{
    width: 170%;
}
.hover{
    gap: 30% !important;
}
.row{
    display: grid;
    grid-template-columns: 40% 40%;
    gap: 15%;
    transition: .4s;
    margin-bottom: 2em;
}
@media screen and (max-width: 1300px) {
    .row{
        grid-template-columns: auto;
        margin-bottom: 1.2em;
        text-align: center;
        gap: 0;
    }
    .hover{
        gap: 0% !important;
    }
    img{
        width: 100%;
    }
    img:hover{
        width: 100%;
    }
    .skill{
        justify-content: center;
    }
}
</style>