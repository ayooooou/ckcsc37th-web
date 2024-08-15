<script setup>
</script>

<template>
  <section id="home">
    <svg id="home_title"viewBox="0 0 1300 1300">
      <!-- Symbol -->
      <symbol id="s-text">
        <text text-anchor="middle" x="50%" y="50%" dy=".35em" id="CKCSC">
          CKCSC
        </text>
      </symbol>
      <use href="#s-text" class="text"></use>
      <use href="#s-text" class="text"></use>
      <use href="#s-text" class="text"></use>
      <use href="#s-text" class="text"></use>
      <use href="#s-text" class="text"></use>
    </svg>
    <p id="th">37th</p>
  </section>
</template>

<style>
#CKCSC {
  margin: 0;
  font-size: 14rem;
  animation-name: fadeIn;
  animation-duration: 0.7s;
  animation-delay: 0.1s;
  animation-fill-mode: forwards;
}

#home_title{
  margin-top: -35%;
  margin-bottom: -40%;
}

#th {
  font-size: 5rem;
  margin: 0;
  margin-left: 70%;
  animation-name: fadeIn;
  animation-duration: 0.5s;
  animation-delay: 0.2s;
  animation-fill-mode: forwards;
}

@media (max-width: 768px) {
  #CKCSC {
    margin: 0;
    font-size: 20rem;
  }
  #th {
    font-size: 3rem;
    margin: 0;
    margin-left: 60%;
    transition: transform 0.5s ease, opacity 0.5s ease;
  }
}

@import url(https://fonts.googleapis.com/css?family=Open+Sans:800);

.text {
  fill: none;
  stroke-width: 6;
  stroke-linejoin: round;
  stroke-dasharray: 70 330;
  stroke-dashoffset: 0;
  animation: stroke 6s infinite linear;
}

.text:nth-child(5n + 1) {
  stroke: #4bbcc2;
  animation-delay: -1.2s;
}
.text:nth-child(5n + 2) {
  stroke: #00a1e9;
  animation-delay: -2.4s;
}
.text:nth-child(5n + 3) {
  stroke: #e9f1df;
  animation-delay: -3.6s;
}
.text:nth-child(5n + 4) {
  stroke: #b9fff9;
  animation-delay: -4.8s;
}
.text:nth-child(5n + 5) {
  stroke: #3aa1bf;
  animation-delay: -6s;
}

@keyframes stroke {
  100% {
    stroke-dashoffset: -400;
  }
}

</style>