<template>
    <h1>
        Portfolio
    </h1>
    <div class="container">
        <div class="switch">
            <ul type="none">
                <li @click="this.switch=project.title" v-for="(project,index) of Projects" :key="index">{{project.title}}</li>
            </ul>
        </div>
        <div>
            <div v-show="this.switch==project.title" class="d" v-for="(project,index) in Projects" :key="index">
                <ProjectVue
                :img=project.img
                :title="project.title"
                :description="project.description"
                :link="project.link"
                :github="project.github"
                :skills="project.skills"
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

    @media screen and (max-width:900px) {
        ul{
            display: grid;
            grid-template-columns: auto;
        }
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
import ts from '../assets/ts.svg'
import users from '../assets/users.jpg'

export default {
    name:'PortfolioVue',
    data(){
        return{
            img:{
                shoe:shoe,
                react:react,
                cafe:cafe,
                users:users
            },
            Projects:[
                {
                    title:'shoe shop',
                    img:shoe,
                    link:'https://adp6.github.io/final_js/',
                    github:'https://github.com/adp6/final_js.git',
                    description:'The shoe shop replica project is a web application that provides a user-friendly interface for customers to browse and purchase shoes online. The project focuses on creating an engaging and visually appealing website design that enhances the overall shopping experience. The application includes everything that online shops use: a shopping cart, a modal window for orders, and a back-end powered by Firebase.',
                    skills:[
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
                    ]
                },
                {
                    title:'react-site',
                    description:'This is my React project, which includes a Forum and a Commercial Page. I designed the commercial page myself using Figma and obtained posts from JSON Placeholder. The Rest API Posts represents the forum, where you can create, delete, and sort posts that are spread across 10 pages. The commercial page is a simple page that showcases programming courses with a responsive layout and transitions using React Router.',
                    img:react,
                    link:'https://adp6.github.io/react-site/',
                    github:'https://github.com/adp6/react-site.git',

                    skills:[
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
                    ]
                },
                {
                    title:'Users',
                    img:users,
                    description:'This is my small TypeScript project in which I implemented a simulation where users retrieve data from JSON Placeholder. Users have the ability to create their own accounts and delete it.',
                    link:'https://adp6.github.io/users/',
                    github:'https://github.com/adp6/users',
                    skills:[
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
                        name:'TypeScript',
                        img:ts,
                        id:Date.now()
                    },
                    {
                        name:'Vue',
                        img:vue,
                        id:Date.now()
                    },
                    {
                        name:'Saas',
                        img:sass,
                        id:Date.now()
                    }
                    ]
                },
                {
                    title:'DesignCafé',
                    img:cafe,
                    description:'This is a simple homework assignment from my front-end courses that utilizes only HTML, CSS, and Bootstrap. It involves creating a Japanese café website with a visually pleasing design achieved through user-friendly colors and a responsive layout. By completing this assignment, I have not only honed my technical skills in HTML, CSS, and Bootstrap but also learned how to create visually striking and user-friendly web interfaces.',
                    link:'https://adp6.github.io/hw9/',
                    github:'https://github.com/adp6/hw9',
                    skills:[
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
                    ]
                }
            ],
            switch:'shoe shop'
        }
    },
    components:{
    ProjectVue,
}
}
</script>