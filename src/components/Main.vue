<script >

import menuMain from '../data/menuMain';
import Cards from './partials/Cards.vue';


export default{
  name:'Main',
  components:{
    Cards
  },
  data(){
    return{
      menuMain,
    }   
  },
  methods:{
    getImagePath(img){
      return new URL(`../assets/img/${img}`, import.meta.url).href;
    }
  }
  
  
}

</script>

<template>

 <main>
  <div class="container">
    <div class="row d-flex justify-content-center">
      <Cards v-for="(item, index) in menuMain" :key="index" :cardObject="item"></Cards> 
    </div>
  </div>
 </main>
 
 
</template>

<style lang="scss" scoped>
.container{
  margin: 100px auto;
}
</style>




