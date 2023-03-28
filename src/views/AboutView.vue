<script setup>
import PublicMenu from '../components/PublicMenu.vue';
import Footer from '../components/Footer.vue';
</script>

<template>
   <PublicMenu/>
  <div class="about">
    <h1>About Page</h1>
  </div>
  <Footer></Footer>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
