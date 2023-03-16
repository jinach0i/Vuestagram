<template>
  <div id="container">
    <Post :Data="Data[i]" v-for="(a,i) in Data" :key="i"/>
    <button class="more-btn" @click="[more(), afterMore() ]">더보기 <font-awesome-icon class="after-more-btn" v-if="this.switch==true" icon="fa-regular fa-circle-check" /></button>
  </div>
</template>

<script>
import Post from '../components/Post.vue';
export default {
    name:'TheContainer',
    components:{
      Post,
    },
    data() {
      return {
        switch: false,
      }
    },
    methods: {
      more() {
        
        this.$axios.get(`https://codingapple1.github.io/vue/more${this.ascNum}.json`)
        .then(a=> {
          console.log(a.data);
          this.Data.push(a.data);
          this.ascNum++;
        })
      },
      afterMore(){
        this.switch=true;
      },
    },
    props:{
      Data:Array,
      ascNum:Number,
    },
}
</script>

<style>
.more-btn{width: 100%; height: 40px; line-height: 40px; display: block; cursor: pointer; font-size: 18px; border: 1px solid black; margin: 8% 0;}
.more-btn:hover{filter: drop-shadow(0 0 3em lightblue);}
</style>