<script setup>
import { ref, watch, onMounted } from 'vue';

// 宣告組件的數據和方法
const sloganText = ref("「成功高中電子計算機研習社 Cheng Gong Computer Study Club」簡稱成功電研CKCSC，是一個成功高中內的學術性社團，在社課會教一些關於資訊領域的課程，會有學長帶你從零開始學，也會有進階班，歡迎學弟加入電研社的大家庭！ 除了教學課程，我們也與IZCC分別是建中資訊、中山資研、景美電資等三校，一同合辦許多活動與聯課，並且也會在放學後與四校共同開設課程，提供四校學弟妹與友校們交流的機會。");
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
</script>


<template>
    <section id="about">
            <h1>關於我們</h1>
        <div class="container">
            <img src="../assets/black_logo.png">
            <p>{{ animatedText }}<span id="caret">&nbsp;</span></p>
        </div>
    </section>
    
</template>

<style>
    body{
        font-family: "Noto Sans TC";
    }
    h1{
        font-size: 5rem;
    }
    img{
        width: 40%;
        height: 40%;
    }
    p{
        font-size: 1.5rem;
        padding: 0 5%;
        overflow: hidden;
        animation: typing 3s steps(12)
    }

    .container{
        display: flex;
        justify-content: center;
        align-items: center;
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
    
</style>
