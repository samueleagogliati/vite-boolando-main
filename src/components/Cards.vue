<script scoped>
    import menuMain from '../data/menuMain';
    export default {
        name:'Main',
        data(){
            return{
            menuMain
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

    <div class="card col-4 m-0 p-0 mt-3" v-for="(item, index) in menuMain" :key="index">
        <img class="" :src="getImagePath(item.primaryImage)">
        <span class="saldi span-rosso-verde" v-if="item.discount">{{ item.discount }}</span>
        <span class="sostenibilità span-rosso-verde" v-if="item.sostenibilita">{{item.sostenibilita}}</span>
        <div class="product-2">
            <img :src="getImagePath(item.secondaryImage)">
        </div>
        <div class="heart"><i class="fa-solid fa-heart"></i>
        </div>
    
        <div class="card-body m-0 p-0 ps-2">
            <p class="m-0 p-0">{{ item.marca }}</p>
            <h6 class="m-0 p-0">{{ item.modello }}</h6>
            <span class="prezzo-saldi">{{ item.lastPrice }} &euro;</span>
            <span class="prezzo" v-if="item.fullPrice"> {{ item.fullPrice }} &euro;</span>
        </div>
    </div>


  
</template>


<style lang="scss" scoped>
@use '../sass/partials/variabiles' as * ;


.card{
    position: relative;
    border: none;
    max-width: 300px;
    img{
        width: 100%;
        margin: 8px;
    }
    h6{
      font-size: 20px;
    }
    &:hover{
      opacity: 1;
      .product-2{
        opacity: 1;
      }
    }

    .span-rosso-verde{
      position: absolute;
      top: 370px;
      z-index: 10;
      color: white;
      font-size: 10px;
      padding: 5px 8px;
    }
    .saldi{
      left: 8px;
      background-color: red;
    }
    .sostenibilità{
      left: 48px;
      background-color: #007E00;
    } 
  }

  .product-2{
      position: absolute;
      top: 0;
      left: 0;
      opacity: 0;
      transition: 0.5s;
  }
  
  .heart{
    position: absolute;
    z-index: 90;
    top: 20px;
    right: 9px;
    background-color: white;
    padding: 10px 10px;
    &:hover{
      color: red;
    }
  }
  .card-body{
    padding-left: 8px;
    margin-bottom: 40px;
    p{
      font-size: 15px;
      font-weight: lighter;
      color: rgba(0, 0, 0, 0.616);
    }
    .prezzo-saldi{
      color: red;
      font-size: 15px;
      font-weight: lighter;
      
    }
    .prezzo{
      text-decoration: line-through;
      font-size: 15px;
      font-weight: lighter;
      color: rgba(0, 0, 0, 0.616);
    }
  }



</style>