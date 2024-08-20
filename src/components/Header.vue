<script>
import { RouterLink, RouterView } from 'vue-router'
export default {
    data() {
        return {
        }
    },
    components: {
        RouterLink,
    },
    mounted() {
    
    
  },
}
</script>

<template>
    <div class="headerShow">
        <RouterLink to="/" class="goHomePage">優美環境清潔</RouterLink>
        

        <RouterLink to="AboutUs" class="goAboutUs">About</RouterLink>
        <div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
    <i class="fa-solid fa-bars"></i>
  </button>
  <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
    <li><a class="dropdown-item" href="#">關於我們</a></li>
    <li><a class="dropdown-item" href="#">服務項目</a></li>
    <li><a class="dropdown-item" href="#">聯絡我們</a></li>
  </ul>
</div>
    </div>

    
    
</template>


<style scoped lang="scss">

.headerShow {
    position: relative; /* 确保它可以有 z-index */
    z-index: 1000; /* 设置一个高的 z-index 值 */
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

    .dropdown{
        margin-right: 4%;
        font-family: "Noto Sans TC", sans-serif;

        .btn-secondary.dropdown-toggle::after {
            display: none;
        }

        .btn-secondary:focus {
            outline: none;
            box-shadow: none;
}

        .btn-secondary{
            font-size: 0.9em;
            background-color: rgb(208, 209, 221);
            border: 1px solid rgb(208, 209, 221);
        }


        .dropdown-item{
            font-family: "Noto Sans TC", sans-serif;
        }
    }

    

    
}




/* PC: 1200px 以上 */
@media (min-width: 1200px) {


  
}
</style>
