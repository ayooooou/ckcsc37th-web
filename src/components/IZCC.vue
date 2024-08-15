<script setup>

</script>


<template>
    <section id="izcc">
        <h1>IZCC</h1>
    <div class="container">
        <a href="https://www.instagram.com/zsisc._.31st/" target="_blank"><img id="zsisc" src="../assets/club/club-3.jpg"></a>
    <div class="row">
        <a href="https://www.instagram.com/infor_37th/" target="_blank"><img id="infor" src="../assets/club/club-1.jpg"></a>
        <a href="https://www.instagram.com/ckcsc37th_diary/" target="_blank"><img id="ckcsc" src="../assets/club/club-2.jpg"></a>
    </div>
    <a href="https://www.instagram.com/cmioc_31st/" target="_blank"><img id="cmioc" src="../assets/club/club-4.jpg"></a>
    </div>

    </section>
</template>

<style scoped>

img{
        width: 200px;
        height: 200px;
        border-radius: 50%;
        animation: rotateAndPause 6s ease infinite; /* 動畫每6秒重複一次 */
}

img:hover{
    animation: none; /* 停止旋轉動畫，避免與縮放動畫衝突 */
    animation: zoom 5s ease; /* 添加縮放動畫 */
    }

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.row {
    display: flex; /* 使這個容器內的圖片水平排列 */
    justify-content: center; /* 圖片在橫排中居中對齊 */
    flex-wrap: wrap; /* 控制圖片換行 */
    gap: 200px; /* 控制圖片間距 */
    width: 100%; /* 確保容器寬度 */
}




@keyframes rotateAndPause {
    0% {
        transform: rotate(0deg);
    }
    50% {
        transform: rotate(360deg); /* 完成旋轉 */
    }
    100% {
        transform: rotate(360deg); /* 保持在旋轉結束的位置 */
        /* 這裡可以設定其他屬性，模擬停頓 */
    }
}

@keyframes zoom {
    0% {
        transform: scale(1);
    }
    1%{
        transform: scale(1.1); /* 縮放到110% */
    }
    100% {
        transform: scale(1.1); /* 縮放到110% */
    }
}


@media (max-width: 768px) {
    img{
        width: 100px;
        height: 100px;
        border-radius: 50%;
        animation: rotateAndPause 6s ease infinite; /* 動畫每6秒重複一次 */
}
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.row {
    display: flex; /* 使這個容器內的圖片水平排列 */
    justify-content: center; /* 圖片在橫排中居中對齊 */
    flex-wrap: wrap; /* 控制圖片換行 */
    gap: 90px; /* 控制圖片間距 */
    width: 100%; /* 確保容器寬度 */
}
}

</style>

