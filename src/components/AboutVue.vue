<template>
    <div class="container">
        <h1>
            About me
        </h1>
        <div class="row">
            <div>
                <Popper hover content="That's literally me">
                <img :src=me alt="me">
                </Popper>
            </div>
            <div>
                <p>
                    I started playing video games 🎮 at the age of 6, and ever since then, I've had a desire to pursue a career related to computers. I began learning front-end development by taking courses and taught myself React and Vue. Coding and creating projects have become my passion, which is evident in my portfolio. My journey started around 2018, when I initially tried learning Python but found myself struggling to understand it. Nevertheless, I was determined to learn programming. {{ more? moreText:null }} 
                </p>
                <span @click="()=>{more = !more}">{{ more? 'show less' : 'show more'}}</span>
            </div>
        </div> 
    </div>
    
</template>

<style scoped>
    h1{
        font-size: 5em;
        text-align: center;
    }
    .row{
        display: grid;
        grid-template-columns: auto auto;
        gap: 15%;
    }
    .row div:nth-child(2){
        margin-top: 100px;
    }
    p{
        font-size: 1.5em;
        line-height: 150%;
        font-weight: 600;
        
    }
    img{
        border-radius: 50px;
        width: 550px;
        transition: .5s;
    }
    img:hover{
        opacity: 0.5;
    }

    span{
        font-size: 2em;
        cursor: pointer;
        color: rgb(199, 155, 78);
        transition: .4s;
        font-weight: 600;
    }
    span:hover{
        font-size: 2.3em;
        color: #4d7bc4;
    }

   


    @media screen and (max-width:1300px) {
        .row{
            grid-template-columns: auto;
            gap: 5%;
        }
        .row div:nth-child(2){
            margin-top: 0px;
        }
        img{
            width: 100%;
        }
    }
    
</style>

<script>
import me from '../assets/me.jpg'
import Popper from "vue3-popper";

export default {
    name: "AboutVue",
    components:{
        Popper
    },
    data(){
        return{
            me:me,
            more:false,
            moreText:"After completing my school exams, I successfully gained admission to university, where I continued my learning journey in front-end development. I have been consistently learning and expanding my skills in this field. However, I understand that being a developer requires more than just hard skills. I am also cultivating a developer mindset, including traits like a growth mindset, embracing discomfort, and maintaining a commitment to constant learning. Currently, I am actively practicing on LeetCode and have plans to delve into back-end development. In addition to programming, I enjoy indulging in hobbies such as watching anime, playing video games, playing the guitar, and occasionally reading books."
        }
    }
}
</script>