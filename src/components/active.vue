<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const list = ref(null);
const box = ref(null);
let timer = null;
let left = ref(0);

const images = [
  { name: "暑訓", full: new URL('../assets/active/20240811_205542.jpg', import.meta.url).href },
  { name: "迎新", full: new URL('../assets/active/IMG_4404.jpg', import.meta.url).href },
  { name: "秋遊", full: new URL('../assets/active/IMG_2344.jpg', import.meta.url).href },
  { name: "耶晚", full: new URL('../assets/active/IMG_20231224_190319.jpg', import.meta.url).href },
  { name: "寒訓", full: new URL('../assets/active/IMG_6764.jpg', import.meta.url).href },
  { name: "春遊", full: new URL('../assets/active/IMG_1357.png', import.meta.url).href },
  { name: "企業參訪", full: new URL('../assets/active/DSC01405.JPG', import.meta.url).href },
  { name: "放課", full: new URL('../assets/active/IMG_0441.jpg', import.meta.url).href },
];

function move() {
  clearInterval(timer);
  timer = setInterval(() => {
    left.value -= 2;
    if (left.value <= -(6 * 300 + images.length * 300 + 10 * (6 + images.length - 1))) { 
      left.value = 0;
    }
    if (list.value) {
      list.value.style.left = left.value + 'px';
    }
  }, 20);
}

onMounted(() => {
  move();

  // 暫停自動滑動
  box.value.onmouseenter = () => {
    clearInterval(timer);
  };
  box.value.onmouseleave = () => {
    move();
  };

  // 移動設備上支援手動滑動
  let startX = 0;
  let scrollLeft = 0;

  box.value.addEventListener('touchstart', (e) => {
    clearInterval(timer);
    startX = e.touches[0].pageX - box.value.offsetLeft;
    scrollLeft = box.value.scrollLeft;
  });

  box.value.addEventListener('touchmove', (e) => {
    const x = e.touches[0].pageX - box.value.offsetLeft;
    const walk = x - startX;
    box.value.scrollLeft = scrollLeft - walk;
  });

  box.value.addEventListener('touchend', () => {
    move(); // 恢復自動滑動
  });
});

onBeforeUnmount(() => {
  clearInterval(timer); // 確保在元件卸載時清除定時器
});

const current = ref(null);
function showName(image){
  current.value = image;
}
</script>

<template>
<section id="active">
    <div v-if="current">
        <h1>Activity {{current.name}}</h1>
    </div>
    <div v-else class="aos">
        <h1>Active</h1>
    </div>
    <div class="box aos" ref="box">
      <div class="list" ref="list">
        <img
            v-for="(image, index) in images" 
            :key="index"
            class="photo"
            :src="image.full"
            alt="image"
            @mouseover="showName(image)"
        />
        <img
            v-for="(image, index) in images" 
            :key="index"
            class="photo"
            :src="image.full"
            alt="image" 
            @mouseover="showName(image)"
        />
      </div>
    </div>
</section>
</template>

<style scoped>
.box { 
  position: relative;
  height: 300px;
  border: 1px solid #000000;
  overflow-x: scroll; /* 允許手動水平滑動 */
  scroll-behavior: smooth; /* 平滑滑動 */
  display: flex;
  justify-content: center;
  align-items: center;
}

.list {
  left: 0px;
  display: flex;
  position: absolute;
}

.photo {
  width: 300px;
  height: 200px;
  border: 3px solid rgb(255, 255, 255);
  border-radius: 10%;
  margin: 30px;
  font-size: 5rem;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: transform 0.5s ease;
}

img:hover {
  transform: scale(1.4);
}

@media (max-width: 768px) {
  img:hover {
    transform: scale(1.2);
  }
}
</style>
