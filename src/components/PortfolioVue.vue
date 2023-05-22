<template>
    <h1>
        Portfolio
    </h1>
    <div class="container">
        <div class="switch">
            <ul type="none">
                <li @click="this.switch='shoe'">shoe shop</li>
                <li @click="this.switch='react-site'">react-site</li>
                <li @click="this.switch='DesignCafé'">DesignCafé</li>
            </ul>
        </div>
        <div>
            <div v-show="this.switch=='shoe'" class="d">
                <ProjectVue 
                :img=img.shoe 
                title="shoe shop" 
                description="The shoe shop replica project is a web application that provides a user-friendly interface for customers to browse and purchase shoes online. The project focuses on creating an engaging and visually appealing website design that enhances the overall shopping experience. The application includes everything that online shops use: a shopping cart, a modal window for orders, and a back-end powered by Firebase." 
                link="https://adp6.github.io/final_js/"
                github="https://github.com/adp6/final_js.git" 
                :skills=shoeSkills />
            </div>
            <div v-show="this.switch=='react-site'" class="d">
                <ProjectVue 
                :img=img.react
                title="react-site" 
                description="This is my React project, which includes a Forum and a Commercial Page. I designed the commercial page myself using Figma and obtained posts from JSON Placeholder. The Rest API Posts represents the forum, where you can create, delete, and sort posts that are spread across 10 pages. The commercial page is a simple page that showcases programming courses with a responsive layout and transitions using React Router." 
                link="https://adp6.github.io/react-site/"
                github="https://github.com/adp6/react-site.git"
                :skills=reactSkills 
                />
            </div>
            <div v-show="this.switch=='DesignCafé'" class="d">
                <ProjectVue
                :img = img.cafe
                title="DesignCafé"
                description="This is a simple homework assignment from my front-end courses that utilizes only HTML, CSS, and Bootstrap. It involves creating a Japanese café website with a visually pleasing design achieved through user-friendly colors and a responsive layout. By completing this assignment, I have not only honed my technical skills in HTML, CSS, and Bootstrap but also learned how to create visually striking and user-friendly web interfaces."
                link="https://adp6.github.io/hw9/"
                github="https://github.com/adp6/hw9"
                :skills=cafeSkills
                />
            </div>
        </div>
    </div>
</template>

<style scoped>
    .d{
        animation: forD 1.8s;
    }
    @keyframes forD {
        0%{opacity: 0;}
        100%{opacity: 1;}
    }
    ul{
        display: flex;
        justify-content: center;
        gap: 2%;
        margin-bottom: 2em;
        padding: 0;
    }
    li{
        font-size: 2em;
        padding: 10px 40px 10px 40px;
        font-weight: 600;
    }
    li:hover{
        cursor: pointer;
        background-color: rgb(199, 155, 78);
        color: black;
    }
</style>

<script>
import shoe from '../assets/shoe shop.jpg'
import react from '../assets/react-site.jpg'
import ProjectVue from '@/UI/ProjectVue.vue'
import html from '../assets/html.svg'
import css from '../assets/css.svg'
import js from '../assets/js.svg'
import vue from '../assets/vue.svg'
import bootstrap from '../assets/bootstrap.svg'
import firebase from '../assets/firebase.svg'
import sass from '../assets/sass.svg'
import reactIcon from '../assets/react.svg'
import figma from '../assets/figma.svg'
import cafe from '../assets/Cafe.jpg'

export default {
    name:'PortfolioVue',
    data(){
        return{
            img:{
                shoe:shoe,
                react:react,
                cafe:cafe
            },
            shoeSkills:[
                {
                    name:'HTML',
                    img:html,
                    id:Date.now()
                },
                {
                    name:'CSS',
                    img:css,
                    id:Date.now()
                },
                {
                    name:'JavaScript',
                    img:js,
                    id:Date.now()
                },
                {
                    name:'Vue3',
                    img:vue,
                    id:Date.now()
                },
                {
                    name:'Bootstrap',
                    img:bootstrap,
                    id:Date.now()
                },
                {
                    name:'FireBase',
                    img:firebase,
                    id:Date.now()
                },
                {
                    name:'Sass',
                    img:sass,
                    id:Date.now()
                }
            ],
            reactSkills:[
                {
                    name:'HTML',
                    img:html,
                    id:Date.now()
                },
                {
                    name:'CSS',
                    img:css,
                    id:Date.now()
                },
                {
                    name:'JavaScript',
                    img:js,
                    id:Date.now()
                },
                {
                    name:'ReactJs',
                    img:reactIcon,
                    id:Date.now()
                },
                {
                    name:'Bootstrap',
                    img:bootstrap,
                    id:Date.now()
                },
                {
                    name:'Figma',
                    img:figma,
                    id:Date.now()
                }
            ],
            cafeSkills:[
                {
                    name:'HTML',
                    img:html,
                    id:Date.now()
                },
                {
                    name:'CSS',
                    img:css,
                    id:Date.now()
                },
                {
                    name:'Bootstrap',
                    img:bootstrap,
                    id:Date.now()
                },
            ],
            switch:'shoe'
        }
    },
    components:{
        ProjectVue,
    }
}
</script>