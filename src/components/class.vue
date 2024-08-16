<script setup>
import { ref } from 'vue';

const images = [
{
    name: "網頁設計",
    full: new URL('../assets/class/web_design.png', import.meta.url).href,
    text: `這門課會帶你從0開始一步一步帶著你寫出一個有美感網頁 ! 我們會使用到的有HTML、CSS、JavaScript。這堂課會從最基礎最基礎的開始，沒有任何程式背景也可以來學 !
這堂課最一開始會帶你學習HTML，HTML是網頁的骨架，會先帶著你學習如何使用html寫出最基礎的網頁，再來會帶你使用CSS來美化你的網頁，讓網頁瞬間升級 ! 最後教你用JavaScript讓網頁可以動起來，且在課程中都會搭配著小實作，讓大家更加熟悉學習到的東西。
課程最後的最後會讓大家自己設計一個網頁，大家可以在課程的最後創造出屬於自己的網頁 !`
  },
  {
    name: "Python",
    full: new URL('../assets/class/python.jfif', import.meta.url).href,
    text: `Python是一款非常適合初學者的程式語言，
    因其語意簡單直白的特性，在行業中非常受歡迎，
    如現在最流行的AI，程式大部分都是由Python撰寫，
    在這個課程中，將會由淺入深，帶著你學會課程內容包含：
    <br>- Python的基礎語法<br>- Python進階用法<br>- 專案實作`
  },
  {
    name: "演算法",
    full: new URL('../assets/class/algorithm.png', import.meta.url).href,
    text: `這門課程將帶你深入理解核心的演算法與資料結構，從基礎到進階，涵蓋排序、遞迴、動態規劃等主題，以及圖論中的最短路徑、最小生成樹等技術，等更多進階主題。你將掌握解決複雜問題的能力，並為競賽與實際應用做好準備。<br>
課程大綱
<div class="container" style="margin-top:5%;">
 <div class="book">
     <p>- STL 上<br>- STL 下</p>
    <div class="cover">
        <p>STL</p>
    </div>
   </div>
  <div class="book">
    <p>- 遞迴觀念<br>- 排序<br>- 枚舉<br>- 二分搜、三分搜<br>- Greedy<br>- 分治</p>
    <div class="cover">
        <p>基本觀念</p>
    </div>
   </div>
  <div class="book">
     <p>- DP 1<br>- DP 2<br>- DP 3</p>
    <div class="cover">
        <p>動態規劃</p>
    </div>
   </div>
   <div class="book">
    <p>- 前綴、差分、並查集<br>- BIT、稀疏表<br>- 線段樹<br>- treap<br>- 動態開點線段樹<br> - 持久化資料結構</p>
    <div class="cover">
        <p>資料結構</p>
    </div>
   </div>
   <div class="book">
    <p>- 圖、存圖、DFS<br>- BFS、二分圖<br>- 最小生成樹、最短路徑<br>- 樹、樹直徑、樹重心<br>- LCA、樹壓平<br>- 找關節點、橋、強連通分量<br>- 樹輕重鍊剖分、重心剖</p>
    <div class="cover">
        <p>圖論</p>
    </div>
   </div>
</div>
`
}
];

const current = ref(null);

function showDetail(image) {
  current.value = image;
}

</script>


<template>
    <section id="class" class="aos">
        <h1 class="aos">Class</h1>
        <div class="container aos">
            <img 
                v-for="(image, index) in images" 
                :key="index" 
                :src="image.full" 
                :alt="image.name"
                class="class_img"
                @click="showDetail(image)"
        />
        </div>

        <div v-if="current">
            <h2>{{current.name}}</h2>
            <p v-html="current.text"></p>
        </div>

    </section>
    
</template>

<style >
h2{
  margin:5% ;
}  
  
    .class_img{
        width: 30%;
        height: 40%;
        margin: 2%;
        transition: transform 0.5s ease; /* 設定動畫效果 */
    }

    p{
        padding: 50%;
        font-size: 1rem;
        padding: 0 5%;
        overflow: hidden;
        animation: typing 3s steps(12);
        white-space: pre-wrap;
    }

    .container{
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .class_img:hover{
        transform: scale(1.2) ;
    }

/* From Uiverse.io by eslam-hany */ 
.book {
  position: relative;
  border-radius: 10px;
  width: 150px;
  height: 200px;
  background-color: whitesmoke;
  -webkit-box-shadow: 1px 1px 12px #000;
  box-shadow: 1px 1px 12px #000;
  -webkit-transform: preserve-3d;
  -ms-transform: preserve-3d;
  transform: preserve-3d;
  -webkit-perspective: 2000px;
  perspective: 2000px;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  color: #000;
  margin-right: 2%;
}

.cover {
  font-size: 2rem;
  top: 0;
  position: absolute;
  background-color: rgb(211, 211, 211);
  width: 100%;
  height: 100%;
  border-radius: 10px;
  cursor: pointer;
  -webkit-transition: all 0.5s;
  transition: all 0.5s;
  -webkit-transform-origin: 0;
  -ms-transform-origin: 0;
  transform-origin: 0;
  -webkit-box-shadow: 1px 1px 12px #000;
  box-shadow: 1px 1px 12px #000;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
}

.book:hover .cover {
  -webkit-transition: all 0.5s;
  transition: all 0.5s;
  -webkit-transform: rotatey(-80deg);
  -ms-transform: rotatey(-80deg);
  transform: rotatey(-80deg);
}

.book p {
  font-size: 0.5rem;
  font-weight: bolder;
}

.cover p {
  font-size: 1rem; /* 這裡設置 cover 裡面的文字大小 */
  font-weight: bolder;
}


@media (max-width: 768px) {
  .book {
  height: 200px;
}
}

</style>