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


const isHovered = ref(false);
const mousePosition = ref({ x: 0, y: 0 });

const handleMouseMove = (event) => {
  const rect = event.target.getBoundingClientRect();
  const x = event.clientX - rect.left;
  const y = event.clientY - rect.top;

  mousePosition.value = { x, y };
};

const handleMouseEnter = () => {
  isHovered.value = true;
};

const handleMouseLeave = () => {
  isHovered.value = false;
};

onMounted(() => {
  window.addEventListener('mousemove', handleMouseMove);
});

onUnmounted(() => {
  window.removeEventListener('mousemove', handleMouseMove);
});
</script>


<template>
    <section id="home">
        <p id="CKCSC" class="highlight-text"
        :style="getHighlightStyle"
      @mouseenter="handleMouseEnter"
      @mouseleave="handleMouseLeave">CKCSC</p>
        <p id="th" :class="{ 'visible': isVisible }">37th</p>
    </section>
</template>

<style>



#CKCSC {
    margin: 0;
    margin-top: -10%;
    font-size: 18rem;
    position: absolute; 
}

#th {
    padding-top: 30%;
    padding-bottom: 0%;
    padding-left: 65%;
    font-size: 10rem;
    position: relative;
    transform: translateX(100%); /* 初始位置在螢幕外 */
    opacity: 0; /* 初始完全隱藏 */
    transition: transform 0.5s ease, opacity 0.5s ease; /* 設置平滑過渡效果 */
}

#th.visible {
    transform: translateX(0); /* 滾動後移動到正確位置 */
    opacity: 1; /* 滾動後完全顯示 */
}

@media (max-width: 768px) {
    #CKCSC {
    margin: 0;
    font-size: 5rem;
    position: absolute; 
}

#th {
    padding-top: 30%;
    padding-bottom: 0%;
    padding-left: 60%;
    font-size: 3rem;
    position: relative;
    transform: translateX(100%); /* 初始位置在螢幕外 */
    opacity: 0; /* 初始完全隱藏 */
    transition: transform 1s cubic-bezier(), opacity 1s cubic-bezier(); /* 設置平滑過渡效果 */
}
}

.text-container {
  background-color: rgb(220, 220, 220);
  color: white;
  font-family: Arial, sans-serif;
}

.highlight-text {
  display: inline-block;
  font-size: 2rem;
  position: relative;
  color: transparent;
  background-image: linear-gradient(90deg, transparent, #ffffff, transparent); /* 背景色線性漸變 */
  background-clip: text;
  -webkit-background-clip: text;
  transition: background-position 0.3s ease, text-shadow 0.3s ease;
}

.highlight-text::before {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  color: transparent;
  background-image: radial-gradient(circle closest-side, rgba(255, 255, 255, 0.7), rgba(255, 255, 255, 0)); /* 白色漸變 */
  background-clip: text;
  -webkit-background-clip: text;
  clip-path: circle(0% at 0 0);
  transition: clip-path 0.3s ease;
}

.highlight-text {
  background-position: var(--x) var(--y); /* 鼠標懸停時背景位置 */
}

.highlight-text:hover::before {
  clip-path: circle(50% at var(--x) var(--y)); /* 鼠標懸停時光點的位置 */
}

.highlight-text:not(:hover)::before {
  clip-path: circle(50% at var(--x) var(--y)); /* 在鼠標移開後保持最後的位置 */
}
</style>
