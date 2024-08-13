<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const isVisible = ref(false);

const handleScroll = () => {
  const scrollPosition = window.scrollY;
  const triggerPosition = 10; // 當滾動超過 10px 時觸發效果

  if (scrollPosition > triggerPosition) {
    isVisible.value = true;
  } else {
    isVisible.value = false;
  }
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
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
    margin-top: -5%;
    font-size: 20rem;
    position: relative; 
}

#th {
    font-size: 20rem;
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
