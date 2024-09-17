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

// .headerShow {
//     width: 100%;
//     min-height: 10dvh;
    

//     .goHomePage{
//         font-family: "Noto Sans TC", sans-serif;
//         margin-left: 5%;
//         color:#909FA6;
//     }

//     .goAboutUs{
//         font-family: "Noto Sans TC", sans-serif;
//         display: none;
//     }

// }

.wrap {
  max-width: 100%;
  margin: 0 auto;
}

.headerTop {
    width: 100%;
    height: 10dvh;
    position: relative; /* 确保它可以有 z-index */
    z-index: 1000; /* 设置一个低于 Header.vue 的 z-index 值 */
    display: flex;
    justify-content: space-between;
    align-items: center;
    // background-color: #81a6ef;
    // background-color: rgb(245, 206, 206);
    background-image: url('/pictures/brick-wall-dark.png');
    backdrop-filter: blur( 4px );
    -webkit-backdrop-filter: blur( 4px );
    

    
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
        font-size: 1.6em;
        font-weight: 746;

        font-family: "Noto Sans TC", sans-serif;
        margin-left: 4%;
        color:#D1E0E9;
        text-decoration: none;
        // text-shadow: 2px 1px 0px #fff, 5px 4px 0px rgba(0, 0, 0, 0.15);
    }

}

.menu {
  max-height: 0px;
  overflow: hidden;
  display: block;
  position: absolute;
  top: 10dvh;
  width: 100%;
  text-align: center;
  background: linear-gradient(135deg, #20c997, #0b5f56);
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
  color: #f0f0f0;
  font-weight: 400;
  font-family: "Noto Sans TC", sans-serif;

  // transition: all 0.5s;
  text-decoration: none;
  width: 100%;
  height: 10dvh;
  padding: 12px 18px;
  margin: 0;


}

// .menu li a:hover {
//   background: #2e2e2e;
//   color: #f5f5dc;
// }

.menu li a .aLine {
  display: block; /* 使 .aLine 成为块级元素 */
  width: 60%; /* 调整线条宽度 */
  margin: 0 auto; /* 使线条居中 */
  border-bottom: 1px solid #f0f0f0; /* 设置线条颜色和厚度 */
  margin-top: 2dvh; /* 调整线条与下一个菜单项之间的间距 */
  transition: border-bottom-color 0.3s ease; /* 添加过渡效果 */
}

.menu li a:hover .aLine {
  border-bottom-color: #f5f5dc; /* 设置悬停时的线条颜色 */
}

.showmenu {
  display: block;
  // color: #69ca62;
  padding: 1em;
  text-decoration: none;

.fa-solid{
  font-size: 1.6em;
  margin-top: 0.7dvh;
  color:#D1E0E9;
  // transition: border-bottom-color 0.3s ease; /* 添加过渡效果 */

}

.fa-solid:hover {

  // color: #FF00FF; 
}

}



.menu-show {
  max-height: 60dvh;
  width: 100%;

}

/* PC: 1200px 以上 */
@media (min-width: 1200px) {

  .headerTop {
    height: 12dvh;

.goHomePage{
  font-size: 2em;
  margin-left: 3%;

    }

}

.menu {
  display: none;
}

.showmenu {
  display: none;

.fa-solid{
  display: none;

  }

.fa-solid:hover {

    }
  }
  
}
</style>
