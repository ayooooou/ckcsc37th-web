<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import nav_components from './components/nav.vue'
import home from './components/home.vue'
</script>

<template>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>CKCSC 37th</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+JP&family=Sarpanch:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+JP&family=Noto+Sans+TC:wght@100..900&family=Sarpanch:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
  </head>
  <body>
    <nav_components/>
    <home/>
  </body>
</template>

<style>
body{
  background-color: #000000;
}

</style>
