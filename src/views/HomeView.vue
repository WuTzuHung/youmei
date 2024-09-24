<script setup>
import { ref, onMounted } from 'vue';

const passingElement1 = ref(null);
const passingElement2 = ref(null);


onMounted(() => {

  if (passingElement1.value) {
    passingElement1.value.classList.add('move');
  }
  if (passingElement2.value) {
    passingElement2.value.classList.add('move');
  }

});

</script>



<template>

<div class="Second">
  <div class="passing-total">
<p class="passing-2" ref="passingElement1">
  <span class="passing-bar">
    <span class="passing-txt">優美環境清潔</span>
  </span>
</p>
<p class="passing-2" ref="passingElement2">
      <span class="passing-bar">
        <span class="passing-txt">您的專業清潔夥伴</span>
      </span>
    </p>
  </div>
</div>

<div class="Third">
  <div class="wow animate__animated animate__fadeInUp ourService"  data-wow-delay="1.3s">
    <img class="broomImg" src="/pictures/flying-broom.png" alt="">
    <h2>服務項目</h2>
  </div>

  <div class=" wow animate__animated animate__fadeInUp aboutUs"  data-wow-delay="0.2s">
    <img class="groupImg" src="/pictures/group.png" alt="">
    <h2>關於我們</h2>
  </div>

  <div class="wow animate__animated animate__fadeInUp contactUs"  data-wow-delay="0.2s">
    <img class="contact-mailImg" src="/pictures/contact-us.png" alt="">
    <h2>聯絡我們</h2>
  </div>

  <div class=" wow animate__animated animate__fadeInUp aboutUs aboutUsPc"  data-wow-delay="1.3s">
    <img class="groupImg" src="/pictures/group.png" alt="">
    <h2>關於我們</h2>
  </div>

  <div class="wow animate__animated animate__fadeInUp contactUs contactUsPc"  data-wow-delay="1.3s">
    <img class="contact-mailImg" src="/pictures/contact-us.png" alt="">
    <h2>聯絡我們</h2>
  </div>

</div>

</template>

<style>

body {
  position: relative; 
  z-index: 500; 
  background-color: #13a988;
  background-image: url('/pictures/brick-wall--dark--640x1136.png');
  background-size: cover;         /* 确保背景图片覆盖整个元素 */
  background-position: center;    /* 背景图片居中显示 */
}

.Second{
  width: 100%;
  height: auto;
  margin-top: 10dvh;
}


.passing-total {
  display: flex;
  flex-direction: column;
}

.passing-txt {
  font-size: 1.8em;
  font-weight: 550;
  font-family: "Noto Sans TC", sans-serif;
  
  color: white;
  opacity: 0; /* 初始隱藏文字 */
  transition: opacity 0.4s ease-in-out; /* 確保文字過度效果 */
}

.passing-2 {
  position: relative;
  display: inline-block;
  overflow: hidden;
}

.passing-bar {
  position: relative;
  display: inline-block;
}

.passing-bar::before {
  content: "";
  display: inline-block;
  width: 0;
  height: 100%;
  position: absolute;
  left: 0;
  top: 0;
  z-index: 0;
  background: #D2D5B8;
}



/* 第一个动画，正常运行 */
.passing-2.move:nth-of-type(1) .passing-bar::before {
  animation: passing-bar-animation 0.25s ease forwards, passing-bar-disappear-animation 0.25s ease forwards 0.3s;
}

.passing-2.move:nth-of-type(1) .passing-txt {
  animation: text-appear-animation 0.25s ease forwards 0.51s;
}

/* 第二个动画，延迟 0.8s 后开始 */
.passing-2.move:nth-of-type(2) .passing-bar::before {
  animation: passing-bar-animation 0.3s ease forwards 0.55s, passing-bar-disappear-animation 0.3s ease forwards 0.85s;
}

.passing-2.move:nth-of-type(2) .passing-txt {
  animation: text-appear-animation 0.3s ease forwards 1.06s;
}

@keyframes passing-bar-animation {
  0% {
    width: 0;
  }
  100% {
    width: 100%;
  }
}

@keyframes passing-bar-disappear-animation {
  0% {
    width: 100%;
    left: 0;
  }
  100% {
    width: 0;
    left: 100%;
  }
}

@keyframes text-appear-animation {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.Third{
  width: 100%;
  height: 180dvh;
  /* background-color: white; */
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  padding: 0.01px;

  .ourService{
    width: 70%;
    height: 37dvh;
    background: rgba( 255, 255, 255, 0.2 );
    box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
    backdrop-filter: blur( 1px );
    -webkit-backdrop-filter: blur( 1px );
    border-radius: 10px;
    border: 1px solid rgba( 255, 255, 255, 0.18 );
    transition: box-shadow 1s, background-color 1s,filter 1s;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: transform 0.3s ease;

    .broomImg{
      width: 30%;
      margin-top: 5dvh;
    }

    h2{
      font-size: 1.8em;
      font-weight: 550;
      font-family: "Noto Sans TC", sans-serif;
      color: white;

      margin-top: 5dvh;
      
    }
  }
  
 


  .aboutUs{
    width: 70%;
    height: 37dvh;
    background: rgba( 255, 255, 255, 0.2 );
    box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
    backdrop-filter: blur( 1px );
    -webkit-backdrop-filter: blur( 1px );
    border-radius: 10px;
    border: 1px solid rgba( 255, 255, 255, 0.18 );
    transition: transform 0.3s ease;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;

    .groupImg{
      width: 30%;
      margin-top: 5dvh;
    }

    h2{
      font-size: 1.8em;
      font-weight: 550;
      font-family: "Noto Sans TC", sans-serif;
      color: white;

      margin-top: 5dvh;
      
    }
  }



  .contactUs{
    width: 70%;
    height: 37dvh;
    background: rgba( 255, 255, 255, 0.2 );
    box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
    backdrop-filter: blur( 1px );
    -webkit-backdrop-filter: blur( 1px );
    border-radius: 10px;
    border: 1px solid rgba( 255, 255, 255, 0.18 );
    transition: transform 0.3s ease;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;

    .contact-mailImg{
      width: 30%;
      margin-top: 5dvh;
    }

    h2{
      font-size: 1.8em;
      font-weight: 550;
      font-family: "Noto Sans TC", sans-serif;
      color: white;

      margin-top: 5dvh;
      
    }
  }

  .aboutUsPc, .contactUsPc{
    display: none;
  }

}



/* iPad: 768 - 1199px */
@media (min-width: 768px) {
    .Container{
  background-color:yellow;
}
}

/* PC: 1200px 以上 */
@media (min-width: 1200px) {

  body {

  background-image: url('/pictures/brick-wall--dark--1920x1080.png');
  background-size: cover;         /* 确保背景图片覆盖整个元素 */
  background-position: center;    /* 背景图片居中显示 */
}

.Second{
  width: 100%;
  height: auto;
  margin-top: 0dvh;
  margin-bottom: 0dvh;
  padding: 0.1px;
}

.passing-total {
  display: flex;
  flex-direction: column;
  margin-top: 10dvh;
}



.passing-txt {
  font-size: 2.6em;

}


    .Third{
      height: auto;
  /* align-items: flex-start; */
  flex-direction: row; 

  .ourService{
    width: 18%;
    margin-bottom: 0dvh;
    margin-left: 0%;
    margin-top: 10dvh;
  }

  .ourService:hover{
    transform: translateY(-40px);
  }

  .aboutUs{
    width: 18%;
    margin-bottom: 0dvh;
    margin-left: 0%;
    animation-delay: 0s;
    margin-top: 10dvh;
    display: none;

  }

  .aboutUs:hover{
    transform: translateY(-40px);
  }

  .contactUs{
    width: 18%;
    margin-bottom: 0dvh;
    margin-left: 0%;
    margin-top: 10dvh;
    display: none;

  }

  .contactUs:hover{
    transform: translateY(-40px);
  }

  .aboutUsPc, .contactUsPc{
    display: block;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
  }

  }

  
  
}

</style>