<template>
    <nav class="container">
        <div>
            <img :src=icon alt="icon">
        </div>
        <ul type="none" v-if="width>1350">
            <li><a href="#Home">Home</a></li>
            <li><a href="#About">About</a></li>
            <li><a href="#Skills">Skills</a></li>
            <li><a href="#Portfolio">Portfolio</a></li>
        </ul>
        <div v-else>
            <div class="menu" @click="()=>{toogle = !toogle}">
                <span class="menu-global menu-top" :class="{ 'menu-top-click':toogle }"></span>
                <span class="menu-global menu-middle" :class="{ 'menu-middle-click':toogle }"></span>
                <span class="menu-global menu-bottom" :class="{ 'menu-bottom-click':toogle }"></span>
            </div>
            <div v-show="toogle" class="burger">
                <ul type="none">
                    <li><a href="#Home">Home</a></li>
                    <li><a href="#About">About</a></li>
                    <li><a href="#Skills">Skills</a></li>
                    <li><a href="#Portfolio">Portfolio</a></li>
                </ul>
            </div>
        </div>
        <div>
            <ModalWindowVue />
        </div>
    </nav>
</template>

<style scoped>
ul{
    display: flex;
    align-items: center;
    gap: 20%;
    justify-content: center;
}
nav{
    margin-top:1em;
    display: flex;
    justify-content: space-between;
    color: rgb(209, 209, 209);
}

nav div:nth-child(3){
    margin-top: 9px;
    text-align: end;
}
.sun{
    position: absolute;
    top: 15%;
    right: 10%;
    width: 180px;
    z-index: -1;
}
.menu {
    cursor: pointer;
    margin: 0 auto;
    margin-top: 9px;
    padding-left: 1.25em;
    position: relative;
    width: 40px;
    height: 40px;
}
.menu-global {
  backface-visibility: hidden;
  position: absolute;
  left: 0;
  border-top: 7px solid white;
  width: 100%;
  transition: 0.55s;
}
.menu-top {
  top: 0;
}
.menu-middle {
  top: 18px;
}
.menu-bottom {
  top: 36px;
}
.menu-top-click {
  backface-visibility: hidden;
  top: 15px;
  transform: rotate(50deg);
  transition: 0.55s;
}
.menu-middle-click {
  opacity: 0;
}
.menu-bottom-click {
  backface-visibility: hidden;
  top: 15px;
  transform: rotate(-410deg);
  transition: 0.55s;
}
.burger{
    margin-top: 2px;
    padding: 20px;
    background-color: white;
    animation: burg 0.55s;
}

@keyframes burg {
    0% {padding-top: 0px;}
    100% {padding-top: 20px;}
}

@media screen and (max-width: 1350px) {
    ul{
        flex-direction: column;
        padding: 0;
    }
    a{
        color: #006eff;
    }
}
</style>

<script>
import icon from '../assets/icon.png'
import ModalWindowVue from '@/UI/ModalWindowVue.vue'
export default {
    name:'HeaderVue',
    components:{ModalWindowVue},
    data(){
        return{
            icon:icon,
            width:window.innerWidth,
            toogle:false,
        }
    },
    mounted(){
        this.width = window.innerWidth
        window.addEventListener("resize",  this.resizeHandler);
    },
    methods:{
        resizeHandler() {
            this.width = window.innerWidth
        }
    }
}
    
</script>