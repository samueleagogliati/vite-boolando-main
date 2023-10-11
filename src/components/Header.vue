<script >

import {menuPersone, menuIcons} from '../data/menuHeader';


export default{
  name:'Header',
  data(){
    return {
      menuPersone,
      menuIcons
    }
  }
  
}

</script>


<template>
  <header>
     <div class="container">
      <!-- MENU -->
      <nav class="menu-person">
          <ul class="m-0 p-0">
            <li v-for="(item, index) in menuPersone" :key="index">
              <a :href="item.href">{{ item.text }}</a>
            </li>
          </ul>
        </nav>
        <!-- LOGO BOOLEAN -->
        <div class="logo-bar">
          <img src="zalando-Logo.png" alt="zalando-logo">
        </div>
        <!-- MENU ICON -->
        <div id="menu-icon-bar h-100">
          <nav>
            <ul class="m-0">
              <li v-for="(item, index) in menuIcons" :key="index">
              <a :href="item.href"><i :class="item.icon"></i></a></li>
            </ul>
          </nav>
        </div>
      </div>
  </header>
</template>



<style lang="scss" scoped>

@use '../sass/partials/variabiles' as *;

header{
  background-color: $orange-color;
  z-index: 999;
  position: fixed;
  box-shadow: 0 0 10px 0 gray;
  width: 100%;
  height: 60px;
  top: 0;
  left: 0;

  .container{
    justify-content: space-between;
    align-items: center;
    width: 75%;
    height: 100%;
    nav{
      ul{
        align-items: center;
        li{
          display: inline-block;
          cursor: pointer; 
          a{ 
            list-style: none;
            color: white;
            font-weight: bold;
            padding-left: 10px;
            text-decoration: none;
            &:hover{
              text-decoration: underline;
            }
          }
        }
      }
    }
    .logo-bar{
      width: 100px;
      img{
        width: 100%;
      }
    }
    
  }
}

  
  





</style>