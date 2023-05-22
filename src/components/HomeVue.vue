<template>
  <div class="container row">
    <div>
      <h2>
        Hi, I am Kucherenko Volodymyr &#128075;
      </h2>
      <h1>
        Front-end developer
      </h1>
      <p>
        I have a passion for coding, and I might have a bit of an obsession with coffee ☕. Alongside my love for creating innovative solutions through code, I also enjoy exploring various other interests such as reading books (📖) and playing the guitar (🎸). I find immense joy in learning something new, even if it's not directly related to coding. One of the reasons I created this portfolio is to showcase my projects and demonstrate my growth mindset. I firmly believe in the power of continuous learning and personal development. With each project I undertake, I embrace the challenge and strive to enhance my skills. So whether it's diving into new coding frameworks, experimenting with different coffee flavors, immersing myself in a captivating book, or strumming away on the guitar, I approach every endeavor with a sense of curiosity and dedication.
      </p>
    </div>
    <!-- <div>
      <h2>Made with <span class="green">Vue3</span></h2>
      <img :src=logo alt="logo">
    </div> -->
  </div>
  <CloudsBg/>

</template>

<script>
import logo from "../assets/logo.png"
import CloudsBg from "@/UI/CloudsBg.vue";
export default {
  name: "HomeVue",
  data(){
    return{
      logo:logo
    }
  },
  components:{
    CloudsBg
  }
}
</script>

<style scoped>
  h2,h1,p{
    font-weight: 600;
    text-align: left;
    font-weight: 700;
  }
  h1{
    color: rgb(199, 155, 78);
    font-size: 4em;
  }
  h2{
    font-size: 2em;
  }
  p{
    font-size: 1.5em;
    line-height: 150%;
    width: 70%;
  }
  .row div:nth-child(2){
    text-align: center;
    margin-top: 0px;
  }
  .row{
    display: flex;
    margin-top: 10em;
    gap: 15%;
    color: #4d7bc4;
  }
  .row div:nth-child(1){
    width: 85%;
  }

  img{
    width: 200px;
  }

@media screen and (max-width:900px) {
  .row{
    flex-direction: column;
  }
  .row div:nth-child(2){
    margin-top: 50px;
  }
  .row div:nth-child(1){
    width: 100%;
  }
  p{
    width: 100%;
  }
}
</style>
