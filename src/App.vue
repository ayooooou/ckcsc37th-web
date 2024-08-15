<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup

import nav_components from './components/nav.vue'
import home_components from './components/home.vue'
import about_components from './components/About.vue'
import class_components from './components/class.vue'
import izcc_components from './components/IZCC.vue'
import active_components from './components/active.vue'

</script>

<template>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>CKCSC 37th</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=IBM+Plex+Sans+JP&family=Noto+Sans+TC:wght@100..900&family=Noto+Serif+TC:wght@200..900&family=Sarpanch:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+JP&family=Noto+Sans+TC:wght@100..900&family=Sarpanch:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
  </head>
  <body>
    <nav_components/>
    <home_components/>
    <about_components/>
    <class_components/>
    <izcc_components/>
    <active_components/>
  </body>
</template>

<style>
body{
  background-color: #000000;
  font-family: "Sarpanch","Noto Sans TC";
  overflow-x: hidden; /* 隱藏水平滾動條 */
  color: #ffffff;
}

h1{
    font-size: 3rem;
    margin-top: 10%;
    margin-left: 5%;
    }

.scrollable-element {
    height: 100vh; /* 設置容器高度 */
    overflow-y: scroll; /* 仍然可以滾動 */
    scrollbar-width: none; /* 對於 Firefox 隱藏滾動條 */
}

.scrollable-element::-webkit-scrollbar {
    width: 0px; /* 對於 Webkit 瀏覽器隱藏滾動條 */
}
@keyframes fadeIn{
            0% {
                opacity: 0.1;
                transform: translateY(-30px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

@media (max-width: 768px) {
    h1{
        font-size: 2rem;
    }

    p{
        font-size: 0.7rem;
        padding: 0 5%;
        overflow: hidden;
        animation: typing 3s steps(12);
    }
}

</style>
