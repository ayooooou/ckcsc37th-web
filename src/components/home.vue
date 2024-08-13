<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const isVisible = ref(false);

const handleWheel = (event) => {
  // 檢查滾動方向，通常是垂直方向
  if (event.deltaY > 0) {
    // 向下滾動
    isVisible.value = true;
  } else if (event.deltaY < 0) {
    // 向上滾動
    isVisible.value = false;
  }
};

onMounted(() => {
  window.addEventListener('wheel', handleWheel);
});

onUnmounted(() => {
  window.removeEventListener('wheel', handleWheel);
});
</script>


<template>
    <p id="CKCSC">CKCSC</p>
    <p id="th" :class="{ 'visible': isVisible }">37th</p>
</template>

<style>
body {
    overflow-x: hidden; /* 隱藏水平滾動條 */
}

#CKCSC {
    margin: 0;
    font-size: 20rem;
    position: absolute; 
}

#th {
    padding-top: 20%;
    padding-bottom: 0%;
    padding-left: 65%;
    font-size: 10rem;
    position: relative;
    transform: translateX(100%); /* 初始位置在螢幕外 */
    opacity: 0; /* 初始完全隱藏 */
    transition: transform 1s ease, opacity 1s ease; /* 設置平滑過渡效果 */
}

#th.visible {
    transform: translateX(0); /* 滾動後移動到正確位置 */
    opacity: 1; /* 滾動後完全顯示 */
}
</style>
