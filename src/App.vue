<script setup>
import NavbarPage from './components/NavbarPage.vue';
import HeroPage from './components/HeroPage.vue'
import FooterPage from './components/FooterPage.vue'
import TabMenu from './components/TabMenu.vue';
</script>

<template>
  <div id="app" class="bg-gray-100 scroll-smooth">
    <NavbarPage></NavbarPage>
    <HeroPage></HeroPage>
    <TabMenu></TabMenu>
    <FooterPage></FooterPage>
  </div>
</template>

<style scoped>
 html,body{
  scroll-behavior: smooth;
 }
</style>
