<script setup>
import { RouterLink } from 'vue-router';
</script>
<template>
   <header>
        <div class="container">
            <p class="logo">Easy Task</p>
            <nav>
              <RouterLink to="/">Servicios</RouterLink>
              <RouterLink to="/about">Sobre Nosotros</RouterLink> 
              <RouterLink to="/login">Login</RouterLink> 
            </nav>
        </div>
    </header>
  </template>

  