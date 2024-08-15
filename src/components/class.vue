<script setup>
import { ref } from 'vue';

const images = [
{
    name: "網頁設計",
    full: new URL('../assets/class/web_design.png', import.meta.url).href,
    text: 'html js css.'
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

<div class="accordion">
  <div class="accordion-item">
    <input type="checkbox" id="item1">
    <label for="item1">1. STL</label>
    <div class="accordion-content">
      <p>- STL 上        <br>- STL 下</p>
    </div>
  </div>

  <div class="accordion-item">
    <input type="checkbox" id="item2">
    <label for="item2">2. 基本觀念</label>
    <div class="accordion-content">
      <p>- 遞迴觀念<br>- 排序<br>- 枚舉<br>- 二分搜、三分搜    <br>- Greedy<br>- 分治</p>
    </div>
  </div>

  <div class="accordion-item">
    <input type="checkbox" id="item3">
    <label for="item3">3. 動態規劃</label>
    <div class="accordion-content">
      <p>- DP 1<br>- DP 2<br>- DP 3       </p>
    </div>
  </div>

  <div class="accordion-item">
    <input type="checkbox" id="item4">
    <label for="item4">4. 資料結構</label>
    <div class="accordion-content">
      <p>- 資節 1：前綴、差分、並查集<br>- 資節 2：BIT、稀疏表<br>- 資節 3：線段樹<br>- 資節 4：treap<br>- 資節 5：動態開點線段樹、持久化資料結構          </p>
    </div>
  </div>

  <div class="accordion-item">
    <input type="checkbox" id="item5">
    <label for="item5">5. 圖論</label>
    <div class="accordion-content">
      <p>- 圖論 1：圖、存圖、DFS、BFS、二分圖<br>- 圖論 2：最小生成樹、最短路徑<br>- 圖論 3：樹、樹直徑、樹重心、LCA、樹壓平              <br>- 圖論 4：找關節點、橋、強連通分量<br>- 圖論 5：樹輕重鍊剖分、重心剖分         </p>
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
    <section id="class">
        <h1>Class</h1>
        <div class="container">
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

    
.accordion {
  width: 100%;
}

.accordion-item {
  margin-bottom: -5%;
  display: flex;
  align-items: center;
  width: fit-content; /* 根據內容自適應寬度 */
}


.accordion-item input[type="checkbox"] {
  display: none;
}

.accordion-item label {
  display: block;
  padding: 10px;
  background-color: #6a6a6af4;
  border-radius:10%;
  color: white;
  cursor: pointer;
  font-weight: bold;
}


.accordion-item .accordion-content {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease;
}

.accordion-item input[type="checkbox"]:checked ~ .accordion-content {
  max-height: 500px; /* 這裡設定最大高度，可以根據內容調整 */
  max-width: 1000px;
  padding: 10px;
}
</style>