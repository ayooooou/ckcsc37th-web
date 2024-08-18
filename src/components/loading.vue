<script setup>
const logoUrl = new URL('../assets/club/club-2.jpg', import.meta.url).href;
window.addEventListener("load", (event) => {
  const allBodyElements = document.body.querySelectorAll("*");
  const loading_img = document.getElementById("loading_img");
  allBodyElements.forEach((element) => {
    element.style.visibility = "visible";
  });
  loading_img.style.display = "none";
});
</script>
<template>
      <img id="loading_img" :src="logoUrl" alt="CKCSC 37th"/>
</template>
<style>
#loading_img{
    height: 10%;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  visibility: visible;
  border-radius: 100%;
}
</style>