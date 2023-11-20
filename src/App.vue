<script setup>
import NavbarPage from './components/NavbarPage.vue';
import HeroPage from './components/HeroPage.vue'
import FooterPage from './components/FooterPage.vue'
</script>

<template>
  <div id="app">
    <NavbarPage></NavbarPage>
    <HeroPage></HeroPage>
    <FooterPage></FooterPage>
  </div>
</template>

<style scoped>
 html,body{
  scroll-behavior: smooth;
 }
</style>
