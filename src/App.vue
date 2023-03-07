<script setup>
import Header from './components/Header.vue';
import Container from './components/Container.vue';
import Footer from './components/Footer.vue';
import Post  from "./assets/post.js";
import axios from 'axios';
</script>

<template>
  <div id="wrap">
    <Header />
    <Container :Data="Data" ref="more"/>
    <Footer />
  </div>
</template>
<script>
export default {
  data() {
    return {
      Data: Post,
      ascNum: 0,
    }
  },
  methods: {
    more() {
      axios.get(`https://codingapple1.github.io/vue/more${ascNum}.json`)
        .then((result) => {
          console.log(result);
        })
    },
  },
  components: {
    Header,
    Container,
    Footer,
  },
}
</script>
<style>
*{padding: 0;}

ul {
  padding: 5px;
  list-style-type: none;
}
button{border: none; background: none;}
#app {
  box-sizing: border-box;
  font-family: "consolas";
  margin-top: 60px;
  width: 100%;
  max-width: 460px;
  margin: auto;
  position: relative;
  border-right: 1px solid #eee;
  border-left: 1px solid #eee;
}
</style>
