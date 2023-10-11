<script >

import { menuOptions, menuFooterIcons } from '../data/menuFooter';

export default{
  name:'Footer',
  data(){
    return{  
      menuOptions,
      menuFooterIcons}
  } 
  
}

</script>

<template>
   <footer>
    <section class="section-footer">
      <div class="container">
        <div>
          <p>Boolando S.r.l</p>
         <nav>
          <ul class="m-0 p-0">
            <li v-for="(item, index) in menuOptions" :key="index">
              <a :href="item.href">{{ item.text }}</a>
            </li>
            
          </ul>
        </nav>
        </div>
        <div class="social-footer">
          <p>Trovaci anche su</p>
          <nav>
            <ul class="m-0 p-0">
              <li v-for="(item, index) in menuFooterIcons" :key="index">
                <a :href="item.href"><i :class="item.icon"></i></a>
              </li>
            </ul>
          </nav>
        </div>
        
      </div>

    </section>
  </footer>
</template>

<style lang="scss" scoped>

 @use '../sass/partials/variabiles' as *;

  footer{
    section{
      background-color: $color-footer;
      height: 90px;  
    }
  }

  .container{
    justify-content: space-between;
    align-items: center;
    width: 75%;
    p{
      top: 5px;
      font-size: 15px;
      font-weight: bold;
      color: white;
      margin: 0;
    }
    
    ul{
      li{
        text-decoration: none;
        display: inline-block;
        padding-right: 10px;
        color: white;
        a{
          text-decoration: none;
          font-size: 12px;
          color: white;
        }
      }
    }
  }
  .social-footer{
    li{
      margin-right: 5px;
    }
  }
  
</style>