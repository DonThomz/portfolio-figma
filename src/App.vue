<template>
  <div class="page">
    <Header first-name="Thomas" last-name="Guillaume"></Header>
<!--    <Background/>-->
    <div class="container-info" id="about">
      <div>
        <p>Hi !</p>
        <p>I’m Thomas Guillaume
          a Front-End Developer</p>
        <p>Front-End devel oper based in Bekasi, Indonesian
          I’am coding with a clean and beautiful problem
          solving in mind.</p>
      </div>
      <img class="header-img" src="./assets/header.svg" alt="">
    </div>

    <div id="passions" class="container-cards">
      <h2>Additional <strong>passions</strong></h2>
      <div class="card-list">
        <Card img="card-1.svg">
          <div class="card-slot">
            <p><strong>Front-End</strong> Developer</p>
            <p class="small-text">(Sass, Bootstrap, Tailwind)</p>
          </div>
        </Card>
        <Card img="card-2.svg">
          <div class="card-slot">
            <p><strong>Back-End</strong> Developer</p>
            <p class="small-text">(NodeJS, Laravel, Codeigniter)</p>
          </div>
        </Card>
        <Card img="card-3.svg">
          <div class="card-slot">
            <p><strong>UI/UX</strong> Designer</p>
            <p class="small-text">(Figma, Zeplin, Adobe XD)</p>
          </div>
        </Card>
      </div>
    </div>
    <div id="portfolio" class="container-cards">
      <h2>My <strong>Portfolio</strong></h2>
      <div class="card-list">
        <Card img="card-1.svg">
          <div class="card-slot">
            <p><strong>Front-End</strong> Developer</p>
            <p class="small-text">(Sass, Bootstrap, Tailwind)</p>
          </div>
        </Card>
        <Card img="card-2.svg">
          <div class="card-slot">
            <p><strong>Back-End</strong> Developer</p>
            <p class="small-text">(NodeJS, Laravel, Codeigniter)</p>
          </div>
        </Card>
        <Card img="card-3.svg">
          <div class="card-slot">
            <p><strong>UI/UX</strong> Designer</p>
            <p class="small-text">(Figma, Zeplin, Adobe XD)</p>
          </div>
        </Card>
      </div>
    </div>
    <div class="container-icons">
      <h2>Contact <strong>Me</strong></h2>
      <div>
        <div class="icon">
          <div :style="{ backgroundImage: 'url(blue-mask.svg)' }">
            <img src="github.svg" alt="">
          </div>
          <h3>Github</h3>
        </div>
        <div class="icon">
          <div :style="{ backgroundImage: 'url(blue-mask.svg)' }">
            <img src="instagram.svg" alt="">
          </div>
          <h3>Instagram</h3>
        </div>
        <div class="icon">
          <div :style="{ backgroundImage: 'url(blue-mask.svg)' }">
            <img src="email.svg" alt="">
          </div>
          <h3>Email</h3>
        </div>
        <div class="icon">
          <div :style="{ backgroundImage: 'url(blue-mask.svg)' }">
            <img src="phone.svg" alt="">
          </div>
          <h3>Tel</h3>
        </div>
      </div>
    </div>
  </div>
  <Footer/>
</template>

<script>

import Header from "./components/Header";
// import Background from "./components/Background";
import {onMounted, ref} from "vue";
import Card from "./components/Card";
import Footer from "./components/Footer";
export default {
  name: 'App',
  components: {
    Footer,
    // Background,
    Card,
    Header
  },
  setup() {
    const amount = 8
    const ellipse = ref([])
    onMounted(() => {
      for (let i = 0; i < amount; i++) {
        ellipse.value.push({
          width: randomIntFromInterval(150, 70),
          height: randomIntFromInterval(150, 70),
          x: randomIntFromInterval(130, window.innerWidth),
          y: randomIntFromInterval(50, window.innerHeight)
        })
      }
    })
    function randomIntFromInterval(min, max) { // min and max included
      return Math.floor(Math.random() * (max - min + 1) + min)
    }
    return { ellipse }
  }
}

</script>

<style lang="scss">
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  @media (max-width: $mobile-breakpoint) {
    margin-top: 0;
  }
}
.page {
  max-width: 1440px;
  margin: 0 auto;
  padding: 42px;
  @media (max-width: $mobile-breakpoint) {
    padding: 0 20px 20px 20px;
  }
}
h2 {
  font-size: 35px;
  font-weight: 400;
  color: #14279B;
}
.header-img {
  width: 100%;
  max-width: 500px;
}
.card-list {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  flex-wrap: wrap;
  .card {
    margin: 20px;
  }
  .card-slot {
    font-size: 25px;
    & > p {
      font-weight: 400;
      margin: 0;
    }
  }
}
#passions, #portfolio {
  margin-bottom: 168px;
}
.container-info {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 50px;
  @media (max-width: $mobile-breakpoint) {
    flex-wrap: wrap-reverse;
    justify-content: center;
  }
  & > div {
    max-width: 592px;
  }
  p {
    margin: 0;
    color: #002265;
    text-align: left;
   &:first-child {
     font-size: 35px;
   }
   &:nth-child(2) {
     font-size: 50px;
     font-weight: 600;
   }
   &:last-child {
     font-size: 23px;
   }
  }
}
.container-cards {
  h2 {
    margin-bottom: 60px;
  }
}
.container-icons {
  & > div {
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    flex-wrap: wrap;
    .icon {
      @media (max-width: $mobile-breakpoint) {
        margin-bottom: 20px;
      }
    }
  }
}
.icon {
  width: 240px;
  height: 240px;
  div {
    background-repeat: no-repeat;
    background-size: contain;
    background-position: center;
    width: 166px;
    height: 160px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto;
  }
  h3 {
    font-weight: 500;
    font-size: 35px;
  }
}
</style>
