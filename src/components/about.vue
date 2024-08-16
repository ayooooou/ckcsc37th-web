<script setup>
import { ref, watch, onMounted } from 'vue';

// 宣告組件的數據和方法
const sloganText = ref(`
簡稱 :「 成功電研 CKCSC 」
全名 :「 成功高中電子計算機研習社 Cheng Gong Computer Study Club 」
介紹 : 我們是一個成功高中內的學術性社團，在社課會教一些關於資訊領域的課程，會有學長帶你從零開始學，也會有進階班，歡迎學弟加入電研社的大家庭！ 除了教學課程，我們也與IZCC分別是建中資訊、中山資研、景美電資等三校，一同合辦許多活動與聯課，並且也會在放學後與四校共同開設課程，提供四校學弟妹與友校們交流的機會。`);
const animatedText = ref("");
let i = ref(0);

const typeWriter = () => {
  const speed = 100;
  if (i.value < sloganText.value.length) {
    animatedText.value += sloganText.value.charAt(i.value);
    i.value++;
    setTimeout(typeWriter, speed);
  }
};

// 監聽 animatedText 的變化
watch(animatedText, (newV) => {
  if (newV === sloganText.value) {
    setTimeout(() => {
      i.value = 0;
      animatedText.value = "";
      typeWriter();
    }, 10000);
  }
});

// 當組件掛載時開始動畫
onMounted(() => {
  setTimeout(() => typeWriter(), 1000);
});

const images = [
  new URL('../assets/logo/blue.png', import.meta.url).href,
  new URL('../assets/logo/black.png', import.meta.url).href,
  new URL('../assets/logo/orange.png', import.meta.url).href,
  new URL('../assets/logo/red.png', import.meta.url).href,
];

// 當前顯示的圖片
const currentImage = ref(images[0]);

let imageIndex = 0;

// 切換到下一張圖片
function changeImage() {
  imageIndex = (imageIndex + 1) % images.length;
  currentImage.value = images[imageIndex];
}
</script>


<template>
    <section id="about" class="aos">
        <h1>About</h1>
        <div class="container">
            <img
            id="logo"
            :src="currentImage"
            @mouseover="changeImage"
            @click="changeImage"
            alt="Logo"
            />
            <p>{{ animatedText }}<span id="caret">&nbsp;</span></p>
        </div>
    </section>
    
</template>

<style scoped>
    p{
        font-size: 1rem;
        padding: 0 5%;
        overflow: hidden;
        animation: typing 10s steps(12)
    }
    
    #logo{
        width: 20%;
        height: 30%;
        margin-left:10%;
        margin-top: 5%;
        border-radius: 100%;
        transition: transform 0.5s ease; /* 設定動畫效果 */
    }

    #logo:hover{
        animation: logo 0.5s;
    }

    @keyframes logo{
      0%{
        opacity: 0.1;
      }
      100%{
        opacity: 1;
      }
    }

    .container{
        display: flex;
        justify-content: left;
        align-items: center;
        border: 3px solid #4bbcc2;
        padding-bottom: 5%;
        border-radius: 2%;
    }
    #caret {
        border-left: 5px solid #4bbcc2;
        margin-left: 3px;
        animation: blink-caret 1s infinite;
    }


    @keyframes blink-caret {
    from {
        border-color: transparent;
    }
    to {
        border-color: #4bbcc2;
    }
}

@media (max-width: 768px) {
  h1{
        font-size: 2rem;
    }
    #logo{
        width: 40%;
        height: 40%;
    }
    p{
        font-size: 0.8rem;
        padding: 0 5%;
        overflow: hidden;
        animation: typing 3s steps(12)
    }
}


</style>
