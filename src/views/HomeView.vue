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

</div>

<div class="Fourth">

</div>
</template>

<style>

body {
  /* font-family: 'Noto Sans JP', sans-serif; */
  background-color: rgba(182, 180, 177, 0.25);
  position: relative; /* 确保它可以有 z-index */
  z-index: 500; /* 设置一个低于 Header.vue 的 z-index 值 */
}

.Second{
  width: 100%;
  height: 18dvh;
  /* background-color: white; */
}


.passing-total {
  display: flex;
  flex-direction: column;
}

.passing-txt {
  font-size: 1.8em;
  font-weight: 400;
  font-family: "Noto Sans TC", sans-serif;
  color: #909FA6;
  opacity: 0; /* 初始状态隐藏文字 */
  transition: opacity 0.4s ease-in-out; /* 确保文字显示有过渡效果 */
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

.passing-2.move .passing-bar::before {
  animation: passing-bar-animation 0.4s ease forwards, passing-bar-disappear-animation 0.4s ease forwards 0.4s;
}

.passing-2.move .passing-txt {
  animation: text-appear-animation 0.4s ease forwards 0.4s; /* 动画结束后显示文字 */
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
  height: 110dvh;
  /* background-color: white; */
}

.Fourth{
  width: 100%;
  height: 30dvh;
  background-color: white;
}



/* iPad: 768 - 1199px */
@media (min-width: 768px) {
    .Container{
  background-color:yellow;
}
}

/* PC: 1200px 以上 */
@media (min-width: 1200px) {
    .Container {
        background-color: red; 
    }
  
}

</style>