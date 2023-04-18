<script setup>
//import { RouterLink, RouterView } from 'vue-router'
import HomeView from './views/HomeView.vue'
import FooterLogin from './views/FooterLogin.vue'
</script>

<template>
  <div class="main-login relative">
    <home-view />
    <FooterLogin class="absolute bottom-[111px]"/>
  </div>

</template>

<style lang="scss" scoped>
.main-login{
  background-color: #E5E5E5;
  height: 100vh;
}
</style>
