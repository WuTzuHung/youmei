<script>
import { RouterLink, RouterView } from 'vue-router'
export default {
    data() {
        return {
            isMenuVisible: false,
        }
    },
    components: {
        RouterLink,
    },
    methods: {
    toggleMenu() {
      this.isMenuVisible = !this.isMenuVisible;
    },
  },
};
</script>

<template>
    <!-- <div class="headerShow">
        <RouterLink to="/" class="goHomePage">優美環境清潔</RouterLink>
        

        <RouterLink to="AboutUs" class="goAboutUs">About</RouterLink>
        
    </div> -->
    <div class="wrap">
    <div class="headerTop">
        <RouterLink to="/" class="goHomePage">優美環境清潔</RouterLink>
      <!-- <div class="logo"></div> -->
      <ul :class="{'menu': true, 'menu-show': isMenuVisible}">
        <li><a href="#">關於我們<div class="aLine"></div></a></li>
        
        <li><a href="#">服務項目<div class="aLine"></div></a></li>
        
        <li><a href="#">聯絡我們<div class="aLine"></div></a></li>
        
        <li><a href="#">回首頁<div class="aLine"></div></a></li>
        
      </ul>
      <a href="#" class="showmenu" @click.prevent="toggleMenu"><i class="fa-solid fa-bars"></i></a>
    </div>
  </div>
    
    
</template>


<style scoped lang="scss">

.headerShow {
    width: 100%;
    min-height: 10dvh;
        // background: rgba( 255, 255, 255, 0.25 );
        // background-color: white;
        box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
        backdrop-filter: blur( 4px );
        -webkit-backdrop-filter: blur( 4px );
        border-bottom-left-radius: 10px; /* 左下角圓角 */
        border-bottom-right-radius: 10px; /* 右下角圓角 */
    display: flex;
    justify-content: space-between;
    // justify-content: center;
    align-items: center;
    // letter-spacing: 2px;
    // font-family: 'Press Start 2P', 'keifontregular', 'Kosugi Maru', cursive;

    .goHomePage{
        font-family: "Noto Sans TC", sans-serif;
        margin-left: 5%;
        color:#909FA6;
    }

    .goAboutUs{
        font-family: "Noto Sans TC", sans-serif;
        display: none;
    }

    

    a {
        // margin: 0 auto 0.3rem auto;
    // margin-top: 5dvh;
    display: flex;
    justify-content: center;
    align-content:center;
        // font-family: 'Press Start 2P', 'Kosugi Maru';
        color: rgba(246, 75, 95, 0.992);
        font-size: 1.2em;
        text-decoration: none;
        text-shadow: 2px 1px 0px #fff, 5px 4px 0px rgba(0, 0, 0, 0.15);

        // &:hover {
        //     border-radius: 10px;
        //     background-color: rgba(129, 255, 196, 0.27);
        //     font-size: 40px;
        //     color: black;
        //     box-shadow: 0px 0px 30px 4px rgba(0, 0, 0, 0.2);
        // }

        // &:active {
        //     border-radius: 10px;
        //     background-color: rgba(0, 0, 0, 0.344);
        // }
    }

}

.wrap {
  max-width: 100%;
  margin: 0 auto;
}

.headerTop {
    position: relative; /* 确保它可以有 z-index */
    z-index: 1000; /* 设置一个低于 Header.vue 的 z-index 值 */
    display: flex;
    justify-content: space-between;
    align-items: center;
    // background-color: #81a6ef;
    background-color: rgb(245, 206, 206);
    

    
    // box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
    //     backdrop-filter: blur( 4px );
    //     -webkit-backdrop-filter: blur( 4px );
        // border-bottom-left-radius: 10px; /* 左下角圓角 */
        // border-bottom-right-radius: 10px; /* 右下角圓角 */

  position: fixed;
  width: 100%;

  margin: 0;
//   background: #0f222b;
// background-color: rgba(182, 180, 177, 0.25);

.goHomePage{
        font-size: 1.4em;
        font-weight: 746;

        font-family: "Noto Sans TC", sans-serif;
        margin-left: 4%;
        color:#909FA6;
        text-decoration: none;
        text-shadow: 2px 1px 0px #fff, 5px 4px 0px rgba(0, 0, 0, 0.15);
    }

}

.menu {
  max-height: 0px;
  overflow: hidden;
  display: block;
  position: absolute;
  top: 9.4dvh;
  width: 100%;
  text-align: center;
  background: white;
  transition: max-height 0.5s;

  //把左邊跑出來的marker去掉
  list-style-type: none;
  padding: 0; /* Remove default padding */
  margin: 0;  /* Remove default margin */
}

.menu li {
  // border: 1px dashed #69ca62;
  height: 10dvh;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0;
}

.menu li a {
  color:#909FA6;
  font-weight: 400;
  font-family: "Noto Sans TC", sans-serif;

  // transition: all 0.5s;
  text-decoration: none;
  width: 100%;
  height: 10dvh;
  padding: 12px 18px;
  margin: 0;


}

.menu li a:hover {
  background: #FFD8F0;
  color: #FF00FF;
}

.menu li a .aLine {
  display: block; /* 使 .aLine 成为块级元素 */
  width: 60%; /* 调整线条宽度 */
  margin: 0 auto; /* 使线条居中 */
  border-bottom: 1px solid #909FA6; /* 设置线条颜色和厚度 */
  margin-top: 2dvh; /* 调整线条与下一个菜单项之间的间距 */
  transition: border-bottom-color 0.3s ease; /* 添加过渡效果 */
}

.menu li a:hover .aLine {
  border-bottom-color: #FF00FF; /* 设置悬停时的线条颜色 */
}

.showmenu {
  display: block;
  // color: #69ca62;
  padding: 1em;
  text-decoration: none;

.fa-solid{
  font-size: 1.6em;
  margin-top: 0.7dvh;
  color:#909FA6;

}

.fa-solid:hover {
  font-size: 1.6em;
  margin-top: 0.7dvh;
  color: #FF00FF; 
}

}



.menu-show {
  max-height: 60dvh;
  width: 100%;

}

/* PC: 1200px 以上 */
@media (min-width: 1200px) {


  
}
</style>
