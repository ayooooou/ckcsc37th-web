<script setup>
const logoUrl = new URL('../assets/loading/logo.png', import.meta.url).href;
</script>

<template>
<nav>
    <div class="main-container left-right">
        <div class="horizontal-item" ><img id="nav_logo" :src="logoUrl" alt="CKCSC 37th"/></div>
        <div class="horizontal-item" >CKCSC</div>
        <div class="horizontal-item" id="Computer-Study-Club">Computer Study Club</div>

        <div class="vertical-container">
            <div class="vertical-item"><a href="#about">About</a></div>
            <div class="vertical-item"><a href="#class">Class</a></div>
        </div>
        <div class="vertical-container">
            <div class="vertical-item"><a href="#izcc">IZCC</a></div>
            <div class="vertical-item"><a href="#active">Activity</a></div>
        </div>

        <div class="vertical-container">
            <div class="vertical-item"><a href="https://linktr.ee/ckcsc37th" target="_blank">linktr.ee</a></div>
            <div class="vertical-item"><a href="https://www.instagram.com/ckcsc37th_diary/"  target="_blank">instagram</a></div>
        </div>
        <div class="horizontal-item" id="location">Taipei, Taiwan</div>
    </div>
</nav>
</template>

<style>
body{
    font-size: 0.8rem;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
}

nav{
    opacity: 0; 
    animation: fadeIn 0.5s ease-out forwards; 
}

#nav_logo{
    width: 20px;
    margin-right: 5px;
}

.left-right a{
  position:relative;
  color: #ffffff;
  text-decoration:none;
}
.left-right a::after{
  content:"";
  display:block;
  width: 0;
  height: 2px;
  background-color: #4bbcc2;
  position:absolute;
  right: 0;
  transition:.4s;
}
.left-right a:hover::after{
  width: 100%;
  left: 0;
}

.main-container {
    display: flex;
    flex-wrap: nowrap;
}

/* 設置每個橫向排列項目的間距 */
.horizontal-item:nth-child(2) {
    margin-right: 5%;
}

.horizontal-item:nth-child(3) {
    margin-right: 30%;
}

/* 設置第一個垂直容器與其他內容之間的間距 */
.vertical-container:nth-child(4) {
    margin-right: 2%; /* 控制第一個垂直容器的右側間距 */
}

.vertical-container:nth-child(5) {
    margin-right: 10%; 
}

.vertical-container:nth-child(6) {
    margin-right: 10%; 
}

@media (max-width: 768px) {
    body {
        font-size: 0.8rem; /* 進一步縮小字體大小 */
    }
    
    .main-container {
    display: flex;
    flex-wrap: nowrap;
    }

    .horizontal-item:nth-child(2) {
        margin-right: 30%;
    }

    .vertical-container:nth-child(5) {
        margin-right: 5%; 
    }

    .vertical-container:nth-child(6) {
        margin-right: 10%; 
    }

    #Computer-Study-Club{
        display: none;
    }

    #location{
        display: none;
    }
}

</style>
