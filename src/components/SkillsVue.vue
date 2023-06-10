<template>
    <h1>My skills</h1>
    <div class="container row">
        <div>
            <p>  
                I create user interfaces that are easy to use, adapt to different devices, and streamline tasks for efficient user experience using these technologies.
            </p>
        </div>
        <div>
            <IconVue :icon="icons.html" name="html" width="100px"/>
            <IconVue :icon="icons.css" name="css" width="100px"/>
            <IconVue :icon="icons.js" name="Javascript" width="100px"/>
            <IconVue :icon="icons.bootstrap" name="bootstrap" width="100px"/>
            <IconVue :icon="icons.figma" name="figma" width="100px"/>
            <IconVue :icon="icons.git" name="git" width="100px"/>
            <IconVue :icon="icons.github" name="github" width="100px"/>
            <IconVue :icon="icons.sass" name="sass" width="100px"/>
            <IconVue :icon="icons.vue" name="Vue 3" width="100px"/>
            <IconVue :icon="icons.react" name="ReactJS" width="100px"/>
            <IconVue :icon="icons.ts" name="TypeScript" width="100px"/>
        </div>
        
    </div>
</template>

<style scoped>
    .row{
        display: flex;
        justify-content: space-around;
        gap: 5%;
    }
    p{
        font-size: 2em;
        font-weight: 600;
        margin-bottom: 50px;
    }
    .row div:nth-child(1){
        width: 50%;
    }
    .row div:nth-child(2){
        display: grid;
        justify-content: center;
        grid-template-columns: auto auto auto auto auto;
        gap: 2%;
        flex-wrap: wrap;
    }
    
    @media screen and (max-width:900px) {
        .row{
            flex-wrap: wrap;
        }
        .row div:nth-child(2){
            display: grid;
            grid-template-columns: auto auto;
        }
        .row div:nth-child(1){
        width: 100%;
        }
    }

</style>

<script>
import IconVue from '@/UI/IconVue.vue'
import html from '../assets/html.svg'
import css from '../assets/css.svg'
import bootstrap from '../assets/bootstrap.svg'
import figma from '../assets/figma.svg'
import git from '../assets/git.svg'
import js from '../assets/js.svg'
import github from '../assets/github.svg'
import sass from '../assets/sass.svg'
import vue from '../assets/vue.svg'
import react from '../assets/react.svg'
import ts from '../assets/ts.svg'

export default {
    name:'SkillsVue',
    components:{
        IconVue
    },
    data(){
        return{
            icons:{
                html:html,
                css:css,
                js:js,
                figma:figma,
                git:git,
                bootstrap:bootstrap,
                github:github,
                sass:sass,
                vue:vue,
                react:react,
                ts:ts
            }
        }
    }
}
</script>