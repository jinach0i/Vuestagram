<template>
  <div id="container">
    <Post :Data="Data[i]" v-for="(a,i) in Data" :key="i"/>
    <button class="more-btn" >+</button>
  </div>
</template>

<script>
import Post from '../components/Post.vue';
export default {
    name:'TheContainer',
    components:{
      Post,
    },
    props:{
      Data:Array,
    },
}
</script>

<style>
button{width: 100%; height: 40px; line-height: 40px; display: block; cursor: pointer; font-weight: bold; font-size: 18px;}
button:hover{filter: drop-shadow(0 0 3em lightblue); }
</style>