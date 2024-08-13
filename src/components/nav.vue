<script setup>

</script>

<template>
<nav>
    <div class="main-container">
        <div class="horizontal-item">CKCSC</div>
        <div class="horizontal-item">Computer Study Club</div>

        <div class="vertical-container">
            <div class="vertical-item">Home</div>
            <div class="vertical-item">About</div>
        </div>
        <div class="vertical-container">
            <div class="vertical-item">Class</div>
            <div class="vertical-item">IZCC</div>
        </div>

        <div class="vertical-container">
            <div class="vertical-item">linktr.ee</div>
            <div class="vertical-item">instergram</div>
        </div>
        <div class="horizontal-item">Taipei, Taiwan</div>
    </div>
</nav>
</template>

<style>
body{
    color: #ffffff;
    font-family: "Sarpanch";
    font-size: 10%;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
}

.main-container {
    display: flex;
    flex-wrap: nowrap;
}

/* 設置每個橫向排列項目的間距 */
.horizontal-item:nth-child(1) {
    margin-right: 5%;
}

.horizontal-item:nth-child(2) {
    margin-right: 40%;
}

/* 設置第一個垂直容器與其他內容之間的間距 */
.vertical-container:nth-child(3) {
    margin-right: 2%; /* 控制第一個垂直容器的右側間距 */
}

.vertical-container:nth-child(4) {
    margin-right: 10%; 
}

.vertical-container:nth-child(5) {
    margin-right: 10%; 
}

@media (max-width: 768px) {
    body {
        font-size: 0.4rem; /* 進一步縮小字體大小 */
    }
    
    .main-container {
    display: flex;
    flex-wrap: nowrap;
    }

    .horizontal-item:nth-child(2) {
        margin-right: 15%;
    }

    .vertical-container:nth-child(4) {
        margin-right: 5%; 
    }

    .vertical-container:nth-child(5) {
        margin-right: 5%; 
    }   
}

</style>
