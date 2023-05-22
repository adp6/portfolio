<template>
  <div id="Home">
    <HeaderVue/>
  </div> 
  <HomeVue />
  
  <section id="About">
    <AboutVue />
  </section>
  
  <section id="Skills">
    <SkillsVue/>
  </section>
  <section id="Portfolio">
    <PortfolioVue />
  </section>
  <ArrowVue/>
  <FooterVue />
</template>

<script>
import HomeVue from './components/HomeVue.vue';
import HeaderVue from './components/HeaderVue.vue';
import AboutVue from './components/AboutVue.vue';
import SkillsVue from './components/SkillsVue.vue';
import ArrowVue from './UI/ArrowVue.vue';
import FooterVue from './components/FooterVue.vue';
import PortfolioVue from './components/PortfolioVue.vue';

export default {
  name: 'App',
  components: {
    HomeVue,
    HeaderVue,
    AboutVue,
    SkillsVue,
    ArrowVue,
    FooterVue,
    PortfolioVue
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
  }
  html {
    scroll-behavior: smooth;
  }
  body{
    background-color: #3f3939;
    font-size: 16px;
    color: rgb(209, 209, 209);
    font-family: "Inter",sans-serif;

  }
  h1{
    text-align: center;
    font-size: 3em;
    color: rgb(199, 155, 78);;
    font-weight: 900;
    margin-top: 50px;
    margin-bottom: 50px;
  }
  a{
    color: white;
    font-weight: 900;
    text-decoration: none;
    font-size: 1.5em;
    position: relative;
    text-decoration: none;
    transition: color .4 ease-out;
  }
  a:hover{
    color: #4d7bc4;
    text-decoration: none;
  }
  a:hover::after{
    border-color: #4d7bc4;
    right: 0;
  }
  a::after{
    content: "";
    border-radius:1em;
    border-top:.1em solid #4d7bc4;
    position: absolute;
    right: 100%;
    bottom: .14em;
    left: 0;
    transition: right .4s cubic-bezier(0,.5,0,1), border-color .4s ease-out;
  }
  
  .container{
    margin: 0 auto;
    width: 80%;
  }

  section {
    margin-top: 250px;
    margin-bottom: 100px;
  }
  #About{
    margin-top: 400px;
  }
  @media screen and (max-width:500px) {
    body{
      font-size: 12px;
    }
  }
</style>
