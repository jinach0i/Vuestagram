<script setup>
import Header from './components/Header.vue';
import Container from './components/Container.vue';
import PostInfo  from "./assets/post.js";
import Footer from './components/Footer.vue';
</script>

<template>
  <div id="wrap">
    <Header />
    <Container :Data="Data" :ascNum="ascNum" />
    <Footer />
  </div>
</template>
<script>
export default {
  data() {
    return {
      Data: PostInfo,
      ascNum: 0,
    }
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
